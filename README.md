# RewardAI Professional — Enhanced Enterprise UI V4

This is the GitHub-ready single-file Streamlit build for **RewardAI Professional**.

Upload only these files to your GitHub repository root:

- `app.py`
- `requirements.txt`
- `README.md`

No `modules`, `templates`, or `docs` folders are required.

## V4 Enhancement

This version applies a more premium enterprise consulting UI inspired by the visual discipline of Fortune 500 SaaS products such as SAP SuccessFactors, Oracle, and Workday.

### Brand system applied

- WEF Blue: `#0082C5`
- Dark Charcoal / Black: `#222222`
- White background: `#FFFFFF`
- Navy Blue: `#003B5C`
- Medium Blue: `#005C8A`
- Light Blue: `#00A3E0`
- Cool Gray: `#8A9A9F`
- Typography: Arial / clean sans-serif

### UI improvements

- Enterprise-style hero section
- Consulting-grade KPI cards
- Refined sidebar treatment
- Cleaner tab styling
- Professional chart palette
- Restored **Compa-Ratio by Grade** box plot with employee dots
- Executive dashboard and pay positioning charts updated with consistent Fortune 500-style visuals
- Data privacy and governance note retained

## V3 upload stability retained

- Safer Excel upload: workbook is selected first, then processed only when the user clicks **Process Uploaded Workbook**.
- File size guard: shows a clear message for files above 15 MB.
- Excel reader uses read-only mode and reads only RewardAI-related sheets.
- Flexible sheet-name handling for common variants such as `Employees`, `Salary Ranges`, `Market Data`, and `Promotions`.
- Flexible column-name aliases for salary and range fields.
- Percent handling accepts `0.06`, `6`, and `6%`.
- Optional sheets are supported.

## Pay positioning definitions

Employee Compa-Ratio = Current Base Salary / Salary Range Midpoint.

Grade Compa-Ratio = Total Current Base Salary in Grade / Total Assigned Midpoint in Grade.

## Run locally

```bash
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

## Deploy on Streamlit Community Cloud

Use:

- Repository: your GitHub repository
- Branch: `main`
- Main file path: `app.py`

## Data privacy note

Use anonymized data for demos. Compensation data is confidential and should be handled according to company HR, Finance, Legal, and privacy controls.
