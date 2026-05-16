# RewardAI Professional — GitHub Ready V2

This is the validated single-file Streamlit build for RewardAI Professional. Upload only these files to your GitHub repository root:

- `app.py`
- `requirements.txt`
- `README.md`

No `modules`, `templates`, or `docs` folders are required.

## What changed in V2

- Safer Excel upload: workbook is read once and cached to prevent repeated re-reading/hanging on every Streamlit rerun.
- File size guard: shows a clear message for files above 15 MB.
- Flexible sheet-name handling for common variants such as `Employees`, `Salary Ranges`, `Market Data`, and `Promotions`.
- Flexible column-name aliases for salary and range fields.
- Safer percent handling: accepts `0.06`, `6`, and `6%`.
- Optional sheets are truly optional: if Market Benchmark or Promotions are not uploaded, the app uses blank outputs instead of mixing sample data with user data.
- Pay positioning correction: Compa-Ratio by Grade is calculated as aggregate salary divided by aggregate midpoint.

## Pay positioning definition

Employee Compa-Ratio = Current Base Salary / Salary Range Midpoint.

Grade Compa-Ratio = Total Current Base Salary in Grade / Total Assigned Midpoint in Grade.

This is stable for mixed structures and equals the average employee compa-ratio when every employee in the same grade has the same midpoint.

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


## V3 Patch Notes
- Restored the Pay Positioning box plot: **Compa-Ratio by Grade** with employee dots.
- Added safer upload processing: file is selected first, then processed only when the user clicks **Process Uploaded Workbook**.
- Excel reader now uses read-only mode and reads only RewardAI-related sheets, reducing Streamlit hanging on larger workbooks.
- Download buttons use cached workbook generation to reduce page refresh delays.
