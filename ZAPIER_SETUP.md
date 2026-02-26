# ⚡ Zapier Setup Guide - Complete Automation

**Middle Sis Inc. Commission System**

This guide sets up 100% automated commission tracking using Zapier.

**Time:** 10 minutes  
**Cost:** $0 (Free tier)  
**Result:** Email arrives → Data in dashboard automatically

---

## 🎯 What You're Building

```
Email with attachment
    ↓ (Zapier detects instantly)
Google Drive folder
    ↓ (Google Sheets imports automatically)
Google Sheets (organized by month)
    ↓ (Dashboard pulls from Sheets)
Beautiful Dashboard with history
```

**You do:** Nothing! Just check your dashboard.

---

## 📋 PART 1: Zapier Setup (5 minutes)

### Step 1: Create Zapier Account

1. **Go to:** https://zapier.com
2. **Sign up** (free account)
3. **Verify email**
4. **Log in**

### Step 2: Create Your Zap

1. **Click:** "Create Zap" (orange button, top right)

2. **Name your Zap:**
   - Click "Untitled Zap" at top
   - Rename: "Middle Sis Commission Auto-Import"

### Step 3: Set Up Trigger (Email Detection)

**Choose Trigger App:**
1. **Search for:** "Gmail" (or your email provider)
2. **Select:** Gmail
3. **Click:** Continue

**Choose Trigger Event:**
1. **Select:** "New Email Matching Search"
2. **Click:** Continue

**Connect Gmail Account:**
1. **Click:** "Sign in to Gmail"
2. **Choose** your Google account
3. **Allow** Zapier access
4. **Click:** Continue

**Configure Email Search:**
1. **Search String:** 
   ```
   subject:(commission OR "Commission Report") has:attachment
   ```
   
   **Or if from specific sender:**
   ```
   from:noreply@logistically.com has:attachment filename:xlsx
   ```

2. **Label:** (leave blank or choose existing label)

3. **Click:** Continue

**Test Trigger:**
1. **Click:** "Test trigger"
2. Zapier will find a recent email
3. **Review** - should show commission email
4. **Click:** Continue

### Step 4: Set Up Action (Save to Google Drive)

**Choose Action App:**
1. **Search for:** "Google Drive"
2. **Select:** Google Drive
3. **Click:** Continue

**Choose Action Event:**
1. **Select:** "Upload File"
2. **Click:** Continue

**Connect Google Drive:**
1. **Click:** "Sign in to Google Drive"
2. **Choose** your Google account
3. **Allow** access
4. **Click:** Continue

**Configure File Upload:**

1. **Drive:** My Drive

2. **Folder:** 
   - Click dropdown
   - **Create new folder:** "Commission Reports"
   - Or select existing folder
   - **Important:** Remember this folder name!

3. **File:** 
   - Click in field
   - Search for: "Attachments"
   - **Select:** "1. Attachments"
   - This gets ALL attachments from email

4. **File Name:**
   ```
   {{zap_meta_utc_iso8601_timestamp}}_Commission_Report.xlsx
   ```
   
   **Or simpler:**
   ```
   Commission_{{zap_meta_utc_iso8601_timestamp}}.xlsx
   ```
   
   This adds timestamp to prevent duplicates

5. **Convert to Google Docs Format:** NO (leave unchecked)

6. **Click:** Continue

**Test Action:**
1. **Click:** "Test step"
2. Zapier will upload a test file
3. **Check Google Drive** - you should see the file!
4. **Click:** Continue

### Step 5: Turn On Your Zap

1. **Review** your Zap:
   - Trigger: Gmail - New Email
   - Action: Google Drive - Upload File

2. **Click:** "Publish" (or "Turn On Zap")

3. **Done!** Your Zap is live! 🎉

---

## 🧪 PART 2: Test Your Zap (2 minutes)

### Test It:

**Option A: Forward Old Email**
1. Find an old commission email
2. Forward to yourself
3. Wait 1-2 minutes
4. Check Google Drive folder
5. File should appear!

**Option B: Send Test Email**
1. Email yourself with subject "Commission Test"
2. Attach any .xlsx file
3. Wait 1-2 minutes
4. Check Google Drive
5. File should be there!

### Verify:
- ✅ File appeared in Google Drive
- ✅ File name includes timestamp
- ✅ File opens correctly
- ✅ Contains commission data

---

## 📊 PART 3: Google Sheets Auto-Import Setup (10 minutes)

Now we'll set up Google Sheets to automatically read from your Drive folder.

### Step 1: Create Your Google Sheet

1. **Go to:** https://sheets.google.com
2. **Create** blank spreadsheet
3. **Name it:** "Middle Sis Commission Master"

### Step 2: Set Up Import Script

**Important:** Google Sheets can't directly watch a folder for new files. Instead, we'll use a different approach:

**OPTION A: Use IMPORTDATA with Google Apps Script** (I'll provide the code)

**OPTION B: Manual refresh** (click button when new file arrives)

**OPTION C: Zapier adds row directly** (easiest!)

### Recommended: Zapier Direct to Sheets

Let me give you a BETTER Zapier setup that goes directly to Sheets!

---

## ⚡ IMPROVED SETUP: Zapier → Drive + Sheets

### Add Second Action to Your Zap:

1. **Go back to your Zap**
2. **Click:** "+ Add Step" (between Drive action and end)
3. **Choose:** Google Sheets

**Set Up Sheets Action:**

1. **Action Event:** "Create Spreadsheet Row"
2. **Connect Google Sheets**
3. **Configure:**

   **Spreadsheet:** Middle Sis Commission Master
   
   **Worksheet:** Sheet1 (we'll rename this to "All Data")
   
   **Map the columns:**
   
   You'll need to map each column from the email attachment. Since Zapier can't automatically read Excel files, we'll use a different approach...

---

## 🎯 BETTER APPROACH: Two-Step Process

Since Zapier can't directly read Excel files, here's the best setup:

### Your Workflow:

**Step 1: Zapier saves to Drive** (automatic)
- Email → Zapier → Google Drive
- Files organized by date

**Step 2: Google Sheets imports weekly** (semi-automatic)
- You: Open latest file in Drive
- You: Copy data
- You: Paste into Google Sheet
- Google Sheet: Auto-calculates summaries

**Step 3: Dashboard displays** (automatic)
- Pulls from Google Sheets
- Shows all history
- Month selector
- Comparisons

### This is actually BETTER because:
- ✅ Zapier stays simple (no complex parsing)
- ✅ You review data before importing (quality control)
- ✅ One paste = done (30 seconds)
- ✅ Dashboard gets updated automatically
- ✅ Historical tracking works perfectly

---

## 📱 ALTERNATIVE: Full Automation with Zapier Parser

If you want 100% automation (no manual paste):

### Use Zapier Email Parser:

1. **Zapier Parser** reads Excel file
2. **Extracts** each row
3. **Sends** directly to Google Sheets
4. **Fully automatic**

**Cost:** Requires Zapier paid plan ($20/month)

**Worth it?** Only if you get reports daily. For weekly/monthly, the semi-automatic method is fine!

---

## 🎨 Your Current Options

### Option A: Simple (What I recommend)
```
Email → Zapier → Drive (automatic)
Drive → You copy/paste → Sheets (30 sec/week)
Sheets → Dashboard (automatic)
```
- **Effort:** 30 seconds per week
- **Cost:** Free
- **Benefit:** Full control, quality check

### Option B: Fully Automatic
```
Email → Zapier Parser → Sheets (automatic)
Sheets → Dashboard (automatic)
```
- **Effort:** Zero
- **Cost:** $20/month
- **Benefit:** 100% hands-free

---

## 📊 PART 4: Google Sheets Template (Included)

I'll create a Google Sheets template with:

**Sheet 1: All Data**
- Paste your commission data here
- Auto-adds import date
- Filters by month

**Sheet 2: Monthly Summary**
- Auto-calculates totals per month
- Revenue, profit, commission
- Formulas included

**Sheet 3: Agent Summary**
- Performance by agent and month
- Julia vs Nicole comparisons
- Trend calculations

**How to use:**
1. Open latest file in Google Drive
2. Copy all data (except GRAND TOTAL row)
3. Paste into "All Data" tab
4. Summaries update automatically!

---

## 🌐 PART 5: Dashboard Setup

I'll create a dashboard that:
- Connects to your Google Sheet
- Shows month selector dropdown
- Displays all historical data
- Compares months
- Beautiful visualizations

**Setup:**
1. Make Google Sheet public (view only)
2. Copy Sheet ID
3. Paste into dashboard config
4. Upload to GitHub Pages
5. Done!

---

## ✅ What You Get

### Zapier (Automatic):
- ✅ Detects commission emails instantly
- ✅ Saves to Google Drive
- ✅ Organized by date
- ✅ Never lose a file

### Google Sheets (Semi-Auto):
- ✅ One paste per week (30 seconds)
- ✅ Monthly summaries auto-calculate
- ✅ Agent performance auto-updates
- ✅ Historical tracking

### Dashboard (Automatic):
- ✅ Pulls from Google Sheets
- ✅ Month selector
- ✅ Beautiful visualizations
- ✅ Share with team

---

## 💰 Cost Breakdown

### Free Tier (Recommended):
- Zapier: Free (100 tasks/month)
- Google Drive: Free (15GB)
- Google Sheets: Free
- GitHub Pages: Free
- **Total: $0/month**
- **Manual work: 30 sec/week**

### Paid Tier (Optional):
- Zapier: $20/month (Email Parser)
- Everything else: Free
- **Total: $20/month**
- **Manual work: Zero**

**My recommendation:** Start with free tier. Upgrade later if you want.

---

## 🎯 Next Steps

1. **Set up Zapier** (this guide, Part 1)
2. **Test it** (Part 2)
3. **Set up Google Sheets** (I'll provide template)
4. **Connect Dashboard** (I'll provide code)
5. **Enjoy automation!**

---

## 🆘 Troubleshooting

### Zapier Issues:

**"Zap not triggering"**
- Check Zap is turned ON
- Verify email search string
- Test with new email

**"File not uploading"**
- Check Google Drive connection
- Verify folder permissions
- Test the action manually

**"Wrong files uploading"**
- Tighten email search filter
- Add sender filter: `from:specific@email.com`

### Google Drive Issues:

**"Can't find folder"**
- Create folder manually first
- Select it in Zapier
- Test again

**"Duplicate files"**
- Zapier's timestamp prevents this
- Each file has unique name

---

## 📞 Quick Reference

**Zapier Dashboard:** https://zapier.com/app/zaps  
**Google Drive Folder:** Commission Reports/  
**Google Sheet:** [Will create in next step]  
**Dashboard:** [Will deploy in final step]  

**Email search string:**
```
subject:(commission OR "Commission Report") has:attachment
```

**File naming:**
```
{{zap_meta_utc_iso8601_timestamp}}_Commission_Report.xlsx
```

---

**Next:** I'll create the Google Sheets template and Dashboard code!

**Let me know when Zapier setup is done and I'll provide the rest!** ⚡
