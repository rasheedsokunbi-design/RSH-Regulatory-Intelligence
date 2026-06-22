# RSH Regulatory Intelligence Portal

A data portal covering 424 registered social housing providers across England,
built and maintained by DG Cities Ltd.

**Live site:** https://ri.dgcities.com

---

## Project structure

```
rsh-portal/
├── data/                          ← Excel source files (update these)
│   ├── RSH_Regulatory_Judgements_Analysis.xlsx
│   ├── 2025_TSM_Full_Data_v1_1_FINAL.xlsx
│   └── 20251211_GA2025_Datafile_for_Publication.xlsx
├── template/
│   └── template.html              ← Portal HTML/CSS/JS (do not edit data here)
├── output/
│   └── index.html                 ← Generated file — deploy this
├── build.py                       ← Run this to regenerate the portal
└── README.md
```

---

## Setup (one time)

1. Install Python 3.10+ from https://python.org
2. Open a terminal in VS Code (`Terminal → New Terminal`)
3. Install the required library:
   ```
   pip install openpyxl
   ```

---

## How to update the portal data

### When RSH publish new Regulatory Judgements:
1. Download the updated spreadsheet
2. Replace the file in `data/RSH_Regulatory_Judgements_Analysis.xlsx`
3. Run `python build.py`
4. Upload `output/index.html` to ri.dgcities.com

### When RSH publish new TSM data:
1. Download the updated TSM file
2. Replace `data/2025_TSM_Full_Data_v1_1_FINAL.xlsx`
   (update the filename in `build.py` line 24 if the name changes)
3. Run `python build.py`
4. Upload `output/index.html`

### When RSH publish new Global Accounts:
1. Download the updated GA file
2. Replace `data/20251211_GA2025_Datafile_for_Publication.xlsx`
   (update the filename in `build.py` line 25 if the name changes)
3. Run `python build.py`
4. Upload `output/index.html`

---

## Running the build

In VS Code, open a terminal and run:
```
python build.py
```

You should see output like:
```
=== RSH Portal Build Script ===

Reading RSH Regulatory Judgements...
  424 providers built, 0 skipped (<1000 homes)
Reading TSM data...
  353 perception, 359 management records
Reading GA2025 financial data...
  173 GA2025 entity records

Generating JavaScript data...
Assembling index.html...

✓ Built successfully!
  Providers: 424
  Output:    output/index.html
  Size:      1,100 KB

→ Deploy output/index.html to ri.dgcities.com
```

---

## Data sources

| File | Source | Frequency |
|------|--------|-----------|
| RSH Regulatory Judgements | RSH website | Published on a rolling basis |
| Tenant Satisfaction Measures | RSH website | Annual (April each year) |
| Global Accounts | RSH website | Annual (December each year) |

---

## Editing the portal design or features

Edit `template/template.html` — this contains all the HTML, CSS and JavaScript
for the portal. The data section is replaced automatically by `build.py` each time
you run it (look for the `%%GENERATED_DATA%%` placeholder in the file — don't 
remove it).

After editing the template, run `python build.py` to apply changes to the output.

---

## Deploying

Upload `output/index.html` to your web server at ri.dgcities.com.
No other files need to be deployed — it's a single self-contained file.

---

## Contact

Built by DG Cities Ltd — https://www.dgcities.com  
13 Soames Walk, London SE10 0AX  
Registered number: 09765525 (England and Wales)
