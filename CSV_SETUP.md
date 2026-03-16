# GitHub CSV Auto-Load Setup

## How It Works
The dashboard now automatically loads data from a `data.csv` file in your GitHub repository. This means you can upload data once and access it from any computer!

## Setup Steps

### 1. Export Your Data
From Logistically TMS, export your commission data as a CSV file.

### 2. Upload to GitHub
1. Go to your GitHub repository: `digitalsalt-it/middlesisinc`
2. Click "Add file" → "Upload files"
3. Upload your CSV file
4. **IMPORTANT: Rename it to exactly `data.csv`** (lowercase, no spaces)
5. Commit the file to the main branch

### 3. Access From Anywhere
- Open the dashboard: https://digitalsalt-it.github.io/middlesisinc/
- The dashboard will automatically load `data.csv` from GitHub
- No need to upload manually!

## Updating Data

To update the data:
1. Go to your repo: `digitalsalt-it/middlesisinc`
2. Click on `data.csv`
3. Click the pencil icon (Edit)
4. Delete all content
5. Paste new CSV data
6. Commit changes
7. Refresh the dashboard (wait 2-3 minutes for GitHub Pages to update)

**OR**

1. Delete the old `data.csv` file
2. Upload new file and rename to `data.csv`

## Manual Override

The "Upload New Data" button still works if you want to test data locally without updating GitHub.

## File Location

The `data.csv` file must be in the **root** of your repository:
```
middlesisinc/
  ├── index.html
  ├── login.html
  ├── data.csv  ← HERE
  └── README.md
```

## Troubleshooting

**Dashboard shows upload screen even with data.csv uploaded:**
- Wait 2-3 minutes after uploading for GitHub Pages to rebuild
- Hard refresh the page: Cmd+Shift+R (Mac) or Ctrl+Shift+R (Windows)
- Check file is named exactly `data.csv` (not `data.csv.csv` or `DATA.CSV`)

**Data is old:**
- Clear browser cache
- Check GitHub repo to confirm latest data is uploaded
- Wait for GitHub Pages rebuild (2-3 minutes)
