# 👥 Authorized Users

This dashboard is restricted to the following email addresses:

## ✅ Allowed Users

1. **austin@middlesisinc.com** - Austin (Middle Sis Inc.)
2. **admin@middlesisinc.com** - Admin (Middle Sis Inc.)
3. **josh@digitalsalt.co** - Josh (Digital Salt)

---

## 🔒 How It Works

When someone tries to log in:

1. They click "Sign in with Microsoft"
2. Microsoft authenticates them (validates their account)
3. **Our dashboard checks** if their email is in the allowed list
4. ✅ **If YES** - They see the dashboard
5. ❌ **If NO** - They see "Access Denied" message and are logged out

---

## ➕ To Add More Users

1. Open `index.html` in a text editor
2. Find this section (around line 735):

```javascript
const ALLOWED_EMAILS = [
    'austin@middlesisinc.com',
    'admin@middlesisinc.com',
    'josh@digitalsalt.co'
];
```

3. Add new email(s):

```javascript
const ALLOWED_EMAILS = [
    'austin@middlesisinc.com',
    'admin@middlesisinc.com',
    'josh@digitalsalt.co',
    'newperson@middlesisinc.com',  // ← Add here
    'another@example.com'           // ← And here
];
```

4. Save and upload to GitHub
5. Wait 2-3 minutes for deployment
6. New users can now log in!

---

## ➖ To Remove Users

1. Open `index.html`
2. Find the `ALLOWED_EMAILS` section
3. Delete or comment out the email:

```javascript
const ALLOWED_EMAILS = [
    'austin@middlesisinc.com',
    'admin@middlesisinc.com',
    // 'josh@digitalsalt.co',  // ← Commented out (removed)
];
```

4. Save and upload
5. That user can no longer access the dashboard

---

## 🔐 Security Notes

**Email matching is case-insensitive:**
- `Austin@MiddleSisInc.com` = `austin@middlesisinc.com` ✅

**Must match exactly:**
- `austin@middlesisinc.com` ✅
- `austin@middlesis.com` ❌ (different domain)
- `austin.smith@middlesisinc.com` ❌ (different email)

**Login still required:**
- Even allowed users must log in with Microsoft
- Can't skip the login screen
- Session expires when they logout

---

## 📊 Current Access

**Total Authorized Users:** 3

**By Organization:**
- Middle Sis Inc.: 2 users
- Digital Salt: 1 user

---

## 🆘 What Users See

### ✅ Authorized User (e.g., austin@middlesisinc.com):
1. Click "Sign in with Microsoft"
2. Log in successfully
3. See dashboard immediately
4. Full access to all features

### ❌ Unauthorized User (e.g., someone@random.com):
1. Click "Sign in with Microsoft"
2. Log in successfully with Microsoft
3. **See error message:**
   ```
   🔒 Access Denied
   
   Your email (someone@random.com) is not authorized 
   to access this dashboard.
   
   Authorized users:
   • austin@middlesisinc.com
   • admin@middlesisinc.com
   • josh@digitalsalt.co
   
   Please contact your administrator if you need access.
   ```
4. Automatically logged out
5. Redirected to login page

---

**Last Updated:** v2.0.1 - Feb 2026
