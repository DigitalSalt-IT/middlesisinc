# 📊 Middle Sis Commission Dashboard v2.0.1

**🔐 Secure Access with Email Whitelist**

---

## 🎯 What's New in v2.0.1

### ✅ Email Whitelist Configured!

**Only these 3 users can access:**
- austin@middlesisinc.com
- admin@middlesisinc.com
- josh@digitalsalt.co

Anyone else who tries to log in will see "Access Denied" and be logged out automatically.

---

## 🚀 Quick Start

### For Authorized Users:

1. Go to your dashboard URL (ending in `/login.html`)
2. Click "Sign in with Microsoft"
3. Log in with your Microsoft account
4. If your email is authorized, you'll see the dashboard!
5. If not authorized, you'll see an access denied message

### For Setup (First Time):

1. Follow `SETUP_MICROSOFT_LOGIN.md` for Azure AD setup
2. Update `login.html` with your Client ID
3. Deploy to GitHub Pages
4. Test with an authorized email

---

## 👥 User Management

**See `AUTHORIZED_USERS.md` for:**
- Current list of allowed users
- How to add new users
- How to remove users
- What unauthorized users see

---

## 🔒 Security Features

**Two-Layer Security:**

**Layer 1 - Microsoft Authentication:**
- Must have valid Microsoft account
- Secure OAuth 2.0 login
- Professional authentication

**Layer 2 - Email Whitelist:**
- Only 3 specific emails allowed
- Case-insensitive matching
- Clear error messages for unauthorized access

**What's Protected:**
- All commission data
- Employee performance info
- Financial calculations
- Everything behind login + whitelist

---

## ✨ All Features

### Security
- ✅ Microsoft OAuth 2.0 login
- ✅ Email whitelist (3 users)
- ✅ Automatic access denial
- ✅ Session management
- ✅ Logout functionality

### Commission Management
- Auto-calculate commission
  - Julia: 5% of profit
  - Nicole: 5% of profit
  - Tom: 15% of profit
  - Austin: 10% of profit
- Shows rate on employee cards
- Total commission calculations

### Performance Tracking
- 40% margin goal tracking
- Green/orange indicators
- Click cards for detailed reviews
- Month-by-month breakdown
- Top 5 best shipments
- 5 lowest margins (coaching)
- AI-powered insights

### Data Management
- Data persistence (localStorage)
- Upload Excel/CSV files
- Export to CSV
- Print reports
- Clear data option

### Design
- Large Middle Sis logo
- Blue/grey branding
- Clean professional look
- Mobile responsive
- User info in header

---

## 📁 Files Included

- **`login.html`** - Microsoft login page (needs Client ID)
- **`index.html`** - Dashboard with email whitelist
- **`SETUP_MICROSOFT_LOGIN.md`** - Azure AD setup guide
- **`AUTHORIZED_USERS.md`** - User management guide
- **`README.md`** - This file
- **`SAMPLE_DATA.xlsx`** - Test data

---

## 🔧 Configuration

### Current Settings:

**Authorized Emails:**
```javascript
austin@middlesisinc.com
admin@middlesisinc.com
josh@digitalsalt.co
```

**Commission Rates:**
```javascript
Julia Matheos: 5.0%
Nicole Caporusso: 5.0%
Tom: 15.0%
Austin: 10.0%
```

**Margin Goal:**
```javascript
40%
```

**To change any of these:** See relevant .md file

---

## 📊 Workflow

1. **Login** - Use authorized Microsoft account
2. **Upload** - Drag commission Excel file
3. **Review** - Check employee performance
4. **Click cards** - View detailed breakdowns
5. **Export** - Download CSV for payroll
6. **Logout** - End session securely

**Time: 3 minutes** ⏱️

---

## 🆘 Support

**Setup Questions:**
→ Read `SETUP_MICROSOFT_LOGIN.md`

**User Management:**
→ Read `AUTHORIZED_USERS.md`

**Login Issues:**
→ Check troubleshooting in setup guide

**Access Denied:**
→ Verify your email is in AUTHORIZED_USERS.md

---

## 📈 Version History

**v2.0.1** - Email Whitelist
- Added 3 authorized emails
- Access denied for unauthorized users
- Clear error messages

**v2.0.0** - Microsoft Login
- Secure authentication
- Login/logout
- Session management

**v1.5.0** - Commission Calculator
- Auto-calculate commissions
- Per-agent rates

---

## ✅ Security Checklist

- [ ] Microsoft login configured (Azure AD)
- [ ] Client ID added to login.html
- [ ] Deployed to GitHub Pages
- [ ] Email whitelist active (3 users)
- [ ] Tested with authorized email
- [ ] Tested with unauthorized email
- [ ] Logout button works

---

**v2.0.1 - Enterprise security with email whitelist!** 🔐✨
