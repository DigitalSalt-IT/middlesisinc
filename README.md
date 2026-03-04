# 📊 Middle Sis Commission Dashboard v1.5.0

**Commission Auto-Calculation!** 💰

---

## 🎯 v1.5.0 - MAJOR UPDATE

### Dashboard Now CALCULATES Commission!

**Commission Rates Set:**
- Julia Matheos: 5% of profit
- Nicole Caporusso: 5% of profit
- Tom: 15% of profit
- Austin: 10% of profit

**How It Works:**
The dashboard reads the Gross Profit column and automatically calculates commission for each person based on their rate.

**Example:**
```
Shipment profit: $1,000
Julia's rate: 5%
Julia's commission: $50 (calculated automatically!)
```

---

## 💡 Why This Matters

**No more manual calculations!**
- Upload file from Logistically
- Dashboard calculates all commissions
- See total owed to each person
- Export for payroll

**Even if the "Sales Commission" column is empty in the Excel file, the dashboard calculates it for you!**

---

## 📊 What You'll See

**Employee Cards:**
```
Julia Matheos
Profit: $6,182.90
Comm Rate: 5.0% of profit
Total Commission: $309.15 ← Auto-calculated!
```

**Total Commission Card:**
```
Total Commission
$725.15 ← Sum of all calculated commissions
5.0% of profit ← Overall average
```

---

## 🔧 To Update Commission Rates

If someone's rate changes:

1. Open `index.html` in text editor
2. Find (around line 730):
```javascript
const COMMISSION_RATES = {
    'Julia Matheos': 5.0,
    'Nicole Caporusso': 5.0,
    'Tom': 15.0,
    'Austin': 10.0
};
```
3. Change the percentage
4. Save and refresh
5. All commissions recalculate automatically!

---

## 📈 The Math

**For each shipment:**
```
Commission = Gross Profit × (Rate / 100)
```

**For Julia at 5%:**
- Shipment 1: $85 profit × 5% = $4.25
- Shipment 2: $174 profit × 5% = $8.70
- Shipment 3: $118 profit × 5% = $5.90
- Total: $309.15

**Dashboard does this for every shipment automatically!**

---

## ✅ Complete Features

- **Auto-calculate commission** (NEW!)
- Shows commission rate on cards (NEW!)
- Commission based on profit % (NEW!)
- Data persistence
- Performance reviews
- 40% margin goal tracking
- Month-by-month analysis
- Export to CSV with calculated commissions
- All calculations correct

---

## 🚀 Workflow

1. **Export from Logistically**
2. **Upload to dashboard**
3. **Commissions calculated automatically**
4. **Click employee cards to review**
5. **Export CSV for payroll**

Done in 2 minutes!

---

**v1.5.0 - No more commission calculation errors!** 💰✨
