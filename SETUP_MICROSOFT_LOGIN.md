# 🔐 Microsoft Login Setup Guide

Follow these steps to enable Microsoft authentication for your Commission Dashboard.

---

## 📋 Prerequisites

- A Microsoft account (Office 365/Azure AD)
- Access to Azure Portal
- 10 minutes of time

---

## 🚀 Step-by-Step Setup

### Step 1: Register Your App in Azure

1. Go to [Azure Portal](https://portal.azure.com)
2. Sign in with your Microsoft account
3. Search for **"Azure Active Directory"** or **"Microsoft Entra ID"**
4. Click **"App registrations"** in the left menu
5. Click **"+ New registration"**

### Step 2: Configure App Registration

**Fill in the form:**

**Name:** `Middle Sis Commission Dashboard`

**Supported account types:** 
- Select **"Accounts in any organizational directory (Any Azure AD directory - Multitenant)"**
- OR **"Accounts in this organizational directory only"** (if you want only your company)

**Redirect URI:**
- Platform: **Web**
- URL: `https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPO-NAME/index.html`
  
  Example: `https://middlesisinc.github.io/commission-dashboard/index.html`

Click **"Register"**

### Step 3: Get Your Client ID

After registration:

1. You'll see your app's **Overview** page
2. Copy the **"Application (client) ID"**
   - It looks like: `12345678-1234-1234-1234-123456789012`
3. Save this for later!

### Step 4: Configure Authentication

1. Click **"Authentication"** in the left menu
2. Under **"Implicit grant and hybrid flows"**, check:
   - ✅ **Access tokens (used for implicit flows)**
   - ✅ **ID tokens (used for implicit and hybrid flows)**
3. Click **"Save"** at the top

### Step 5: Add API Permissions

1. Click **"API permissions"** in the left menu
2. Click **"+ Add a permission"**
3. Select **"Microsoft Graph"**
4. Select **"Delegated permissions"**
5. Search for and check: **"User.Read"**
6. Click **"Add permissions"**

### Step 6: Update Your Dashboard Files

**Open `login.html` in a text editor:**

Find this section:
```javascript
const CONFIG = {
    clientId: 'YOUR_CLIENT_ID_HERE',  // ← Change this!
    redirectUri: window.location.origin + window.location.pathname.replace('login.html', 'index.html'),
    authority: 'https://login.microsoftonline.com/common',
    scopes: ['user.read']
};
```

Replace `YOUR_CLIENT_ID_HERE` with your actual Client ID from Step 3.

**Example:**
```javascript
const CONFIG = {
    clientId: '12345678-1234-1234-1234-123456789012',
    redirectUri: window.location.origin + window.location.pathname.replace('login.html', 'index.html'),
    authority: 'https://login.microsoftonline.com/common',
    scopes: ['user.read']
};
```

### Step 7: Deploy to GitHub Pages

1. Upload both `login.html` and `index.html` to your GitHub repo
2. Commit and push
3. Go to repo Settings → Pages
4. Ensure Pages is enabled
5. Wait 2-3 minutes for deployment

### Step 8: Test!

1. Go to: `https://YOUR-USERNAME.github.io/YOUR-REPO/login.html`
2. Click "Sign in with Microsoft"
3. Sign in with your Microsoft account
4. You should be redirected to the dashboard!

---

## 🔒 Security Notes

**Who can log in?**
- Anyone with a Microsoft account (if you selected "Multitenant")
- Only your organization (if you selected "Single tenant")

**To restrict to specific emails:**

Open `index.html` and add at the top of the script section:

```javascript
// Allowed email addresses
const ALLOWED_EMAILS = [
    'you@middlesisinc.com',
    'manager@middlesisinc.com',
    'admin@middlesisinc.com'
];

// Check on page load
window.addEventListener('DOMContentLoaded', () => {
    const userEmail = sessionStorage.getItem('ms_email');
    
    if (!userEmail) {
        // Not logged in, redirect to login
        window.location.href = 'login.html';
        return;
    }
    
    if (!ALLOWED_EMAILS.includes(userEmail.toLowerCase())) {
        alert('Access denied. Your account is not authorized.');
        sessionStorage.clear();
        window.location.href = 'login.html';
        return;
    }
    
    // Proceed with normal dashboard loading
    loadSavedData();
});
```

---

## ✅ Checklist

- [ ] Created Azure AD App Registration
- [ ] Copied Client ID
- [ ] Enabled implicit grant (access + ID tokens)
- [ ] Added User.Read permission
- [ ] Updated `login.html` with Client ID
- [ ] Deployed to GitHub Pages
- [ ] Tested login flow
- [ ] (Optional) Added email whitelist

---

## 🆘 Troubleshooting

**"Redirect URI mismatch" error:**
- Check that the URL in Azure AD exactly matches your GitHub Pages URL
- Make sure it ends with `/index.html`
- No trailing slashes!

**Login button does nothing:**
- Check browser console for errors
- Make sure you replaced `YOUR_CLIENT_ID_HERE` with actual ID

**"Access denied" after login:**
- If you added email whitelist, check the email is in the list
- Check sessionStorage in browser DevTools

**Still stuck?**
- Check Azure AD app Overview for status
- Verify redirect URI is correct
- Try logging out and back in

---

## 📞 Support

**Microsoft Documentation:**
- [Azure AD App Registration](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)
- [OAuth 2.0 Implicit Flow](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-implicit-grant-flow)

---

**Once configured, your dashboard is secure and professional!** 🔐✨
