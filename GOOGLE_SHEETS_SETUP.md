# 📊 Google Sheets Setup Guide

**Automated Monthly Summaries & Historical Tracking**

Once Zapier saves files to Drive, this Google Sheet becomes your central dashboard.

---

## 🎯 What This Sheet Does

### Automatic Features:
- ✅ Calculates monthly totals
- ✅ Tracks agent performance
- ✅ Compares month-over-month
- ✅ Filters by date, agent, status
- ✅ Never needs formulas updated

### Your Work:
- Paste new data once per week (30 seconds)
- Everything else is automatic!

---

## 🚀 SETUP (10 Minutes)

### Step 1: Create the Spreadsheet

1. **Go to:** https://sheets.google.com
2. **Click:** Blank spreadsheet
3. **Name it:** "Middle Sis Commission Master"
4. **Bookmark this URL!**

### Step 2: Set Up Tabs

**Create 3 tabs:**

1. **Tab 1:** Rename to "All Data"
2. **Tab 2:** Create new → Name "Monthly Summary"
3. **Tab 3:** Create new → Name "Agent Summary"

---

## 📋 TAB 1: All Data Setup

This is where you'll paste commission data.

### Column Headers (Row 1):

Copy these EXACT headers into Row 1:

```
A: Import Date
B: Month
C: Order Number
D: Commission Record ID
E: Commission Create Date
F: Commission Status
G: Customer Name
H: Carrier Name
I: Shipment Date
J: Carrier Cost from Order
K: Customer Total Cost from Order
L: Sales Tax
M: Sales Tax 2
N: Agent Type
O: Agent Full Name
P: Gross Profit
Q: Sales Commission
```

### Format Row 1:
1. **Select** A1:Q1
2. **Format:**
   - Bold
   - Background color: #0F3D3E (dark green)
   - Text color: White
   - Center align

3. **Freeze** Row 1:
   - View → Freeze → 1 row

### Add Import Date Formula (Column A):

**In cell A2, paste:**
```
=IF(C2="","",TODAY())
```

**Then drag down** to A1000

**What this does:** Automatically adds today's date when you paste data

### Add Month Formula (Column B):

**In cell B2, paste:**
```
=IF(C2="","",TEXT(I2,"MMM YYYY"))
```

**Then drag down** to B1000

**What this does:** Extracts month from Shipment Date (e.g., "Feb 2026")

### Set Column Widths:
- A (Import Date): 110px
- B (Month): 90px
- C-Q: Auto-fit or 120px each

---

## 📊 TAB 2: Monthly Summary Setup

Automatically calculates totals per month.

### Headers (Row 1):

```
A: Month
B: Shipments
C: Total Revenue
D: Total Cost
E: Total Profit
F: Total Commission
```

### Format Row 1:
- Bold, dark green background, white text

### Add Data Formula (Starting Row 2):

**Cell A2 - List unique months:**
```
=UNIQUE(FILTER('All Data'!B:B, 'All Data'!B:B<>""))
```

**Cell B2 - Count shipments:**
```
=COUNTIF('All Data'!B:B, A2)
```

**Cell C2 - Sum revenue:**
```
=SUMIF('All Data'!B:B, A2, 'All Data'!K:K)
```

**Cell D2 - Sum cost:**
```
=SUMIF('All Data'!B:B, A2, 'All Data'!J:J)
```

**Cell E2 - Sum profit:**
```
=SUMIF('All Data'!B:B, A2, 'All Data'!P:P)
```

**Cell F2 - Sum commission:**
```
=SUMIF('All Data'!B:B, A2, 'All Data'!Q:Q)
```

### Format Numbers:
- Select C2:F100
- Format → Number → Currency

### Auto-Updates:
These formulas update automatically when you add data to "All Data" tab!

---

## 👥 TAB 3: Agent Summary Setup

Tracks performance by agent and month.

### Headers (Row 1):

```
A: Agent Name
B: Month  
C: Shipments
D: Total Revenue
E: Total Profit
F: Total Commission
G: Avg Margin %
```

### Format Row 1:
- Bold, dark green background, white text

### Add Data (Manual or Formula):

**Option A: Pivot Table (Easiest)**

1. **Go to "All Data" tab**
2. **Select** all data (A1:Q1000)
3. **Insert** → Pivot table
4. **Place in:** "Agent Summary" tab

**Configure Pivot:**
- Rows: Agent Full Name, Month
- Values: 
  - COUNT of Order Number (Shipments)
  - SUM of Customer Total Cost (Revenue)
  - SUM of Gross Profit
  - SUM of Sales Commission

**Option B: QUERY Formula** (Advanced)

**In A2:**
```
=QUERY('All Data'!A:Q, "SELECT O, B, COUNT(C), SUM(K), SUM(P), SUM(Q) WHERE C is not null GROUP BY O, B ORDER BY O, B DESC", 1)
```

This creates a dynamic agent summary!

### Format:
- Currency columns: D, E, F
- Percentage column: G

---

## 🔄 How to Use Your Sheet

### Weekly Routine (30 seconds):

**When new commission email arrives:**

1. **Zapier** saves it to Google Drive automatically
2. **You:** Open Google Drive → Commission Reports folder
3. **You:** Open latest file
4. **You:** Select all data (except GRAND TOTAL row)
   - Shortcut: Ctrl+A, then Shift+Up Arrow to deselect header
5. **You:** Copy (Ctrl+C)
6. **You:** Go to your Google Sheet → "All Data" tab
7. **You:** Click first empty row
8. **You:** Paste (Ctrl+V)

**Done!** Summaries update automatically!

---

## 💡 Pro Tips

### Tip 1: Filter by Month
1. Select "All Data" tab
2. Data → Create a filter
3. Click Month dropdown
4. Select specific month

### Tip 2: Sort by Commission
1. Click column Q header (Sales Commission)
2. Right-click → Sort Z→A
3. See highest commissions first

### Tip 3: Find Negative Profits
1. Click column P (Gross Profit)
2. Format → Conditional formatting
3. Less than: 0
4. Color: Red background

### Tip 4: Highlight by Agent
1. Select "All Data"
2. Format → Conditional formatting
3. Custom formula: `=$O2="Julia Matheos"`
4. Color: Light blue background
5. Repeat for Nicole with different color

---

## 📱 Mobile Access

### iPhone/Android:
1. **Install:** Google Sheets app
2. **Open** your sheet
3. **Pin** to favorites
4. **View** anytime, anywhere!

### Features on Mobile:
- ✅ View all data
- ✅ Filter by month/agent
- ✅ See summaries
- ❌ Can't paste data (need desktop for that)

---

## 🔐 Sharing with Team

### Share View-Only Access:

1. **Click:** Share (top right)
2. **Add** team members' emails
3. **Set to:** Viewer
4. **Click:** Send

### Or Public Link:

1. **Click:** Share
2. **Change:** "Anyone with the link"
3. **Set to:** Viewer
4. **Copy link**
5. **Share** link with team

**Security:** View-only = can't edit your data!

---

## 📊 Sample Data Structure

### After Pasting Data:

```
| Import Date | Month    | Order#     | Customer    | Agent         | Revenue | Commission |
|-------------|----------|------------|-------------|---------------|---------|------------|
| 2/25/2026   | Feb 2026 | ERIX123... | Erixmar     | Julia Matheos | $575.00 | $13.40     |
| 2/25/2026   | Feb 2026 | FSL125...  | Foppiani    | Julia Matheos | $285.00 | $4.25      |
| 2/25/2026   | Feb 2026 | IQNJ127... | Interglobo  | Nicole C.     | $385.00 | $8.70      |
```

### Monthly Summary Shows:

```
| Month    | Shipments | Revenue    | Cost       | Profit    | Commission |
|----------|-----------|------------|------------|-----------|------------|
| Feb 2026 | 78        | $51,191.55 | $36,688.47 | $14,503.08| $725.15    |
| Jan 2026 | 65        | $44,200.00 | $32,100.00 | $12,100.00| $605.00    |
```

### Agent Summary Shows:

```
| Agent         | Month    | Shipments | Revenue    | Commission |
|---------------|----------|-----------|------------|------------|
| Julia Matheos | Feb 2026 | 34        | $17,871.50 | $309.14    |
| Nicole C.     | Feb 2026 | 44        | $33,320.05 | $416.01    |
| Julia Matheos | Jan 2026 | 28        | $15,200.00 | $280.00    |
```

---

## 🎨 Optional: Make It Pretty

### Color Code Agents:

**Julia Matheos rows → Light Blue**
1. Select column O (Agent Full Name)
2. Format → Conditional formatting
3. Format cells if: Text contains "Julia"
4. Background: Light blue 2

**Nicole Caporusso rows → Light Green**
1. Same steps
2. Text contains: "Nicole"
3. Background: Light green 2

### Add Sparklines (Mini Charts):

**In Monthly Summary, add column G:**
- Header: "Trend"
- Formula: `=SPARKLINE(C2:C, {"charttype","line"})`
- Shows revenue trend over months!

---

## 🔄 Maintenance

### Never Need To:
- ❌ Update formulas
- ❌ Recreate sheets
- ❌ Rebuild summaries
- ❌ Recalculate totals

### Only Need To:
- ✅ Paste new data weekly (30 sec)

**That's it!**

---

## 📞 Quick Reference

**Sheet Name:** Middle Sis Commission Master  
**Tab 1:** All Data (paste data here)  
**Tab 2:** Monthly Summary (auto-calculates)  
**Tab 3:** Agent Summary (auto-calculates)  

**Paste location:** First empty row in "All Data"  
**Frequency:** Weekly or when new report arrives  
**Time required:** 30 seconds  

---

## ✅ Setup Checklist

- [ ] Created Google Sheet
- [ ] Named it "Middle Sis Commission Master"
- [ ] Created 3 tabs (All Data, Monthly Summary, Agent Summary)
- [ ] Added headers to All Data tab
- [ ] Added Import Date formula (column A)
- [ ] Added Month formula (column B)
- [ ] Formatted headers (bold, green, white text)
- [ ] Froze row 1
- [ ] Set up Monthly Summary formulas
- [ ] Set up Agent Summary (pivot or query)
- [ ] Tested with sample data
- [ ] Bookmarked sheet URL
- [ ] Shared with team (optional)

---

## 🎉 You're Ready!

Your Google Sheet is now set up for automatic summaries!

**Next:** Connect your dashboard to this sheet for beautiful visualizations!

**See:** `DASHBOARD_CONNECTION.md` for the final step!
