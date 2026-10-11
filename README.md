# E-commerce Sales & Profit Analytics

**Internship submission:** AICTE | IBM SkillsBuild Data Analytics with AI — BharatCares  
**Prepared by:** Aarti Katkar

## Project description
This project analyzes the provided practice workbook `AI + Data_ Make Data Intelligent _ Masterclass 1 _ Practice Dataset.xlsx`. It performs data profiling and quality checks, standardizes date/text/currency formats, flags suspicious quantity values, calculates sales KPIs, and visualizes revenue/profit by category, region, product, and month.

## Dataset
- **Dataset file:** `AI + Data_ Make Data Intelligent _ Masterclass 1 _ Practice Dataset.xlsx`
- **Sheet used:** `Raw_Data` (2,000 rows and 9 columns in the supplied workbook)
- **Source:** Supplied with the AI + Data: Make Data Intelligent masterclass practice materials. No public download URL was provided with the file; do not invent one.
- The notebook prompts you to upload the workbook in Google Colab if it is not already present.

## Technologies
Python, pandas, NumPy, Matplotlib, openpyxl, Jupyter Notebook / Google Colab.

## Files
- `Aarti_EcommerceSalesAnalytics.ipynb` — complete notebook
- `requirements.txt` — Python dependencies
- `Aarti_ProjectReport.docx` — project report
- `README.md` — overview and run instructions

## Run in Google Colab
1. Open https://colab.research.google.com/
2. Upload `Aarti_EcommerceSalesAnalytics.ipynb`.
3. Upload the supplied `.xlsx` workbook when the notebook prompts you, or upload it into the Colab session before running the load cell.
4. Install dependencies by uploading `requirements.txt` and running `!pip install -r requirements.txt`, or run `!pip install pandas numpy matplotlib openpyxl`.
5. Run notebook cells from top to bottom.
6. Review the data-quality audit, charts, KPI values, and exported CSV summaries.

## Run locally on Windows
1. Put the notebook and the supplied Excel workbook in the same folder.
2. Install Python 3.10 or newer.
3. Open Command Prompt in that folder and run:
   - `python -m venv .venv`
   - `.venv\\Scripts\\activate`
   - `python -m pip install -r requirements.txt`
   - `jupyter notebook`
4. Open the notebook and run all cells.

## Cleaning decisions
- Dates are parsed using ISO or day-first formats; invalid dates are marked missing and reported.
- Revenue currency labels and symbols are stripped before conversion to numeric values.
- Category, product, and region labels are standardized by trimming whitespace and title-casing.
- Duplicate `Order_ID` records are deduplicated by keeping the first occurrence.
- Negative quantities are flagged and excluded from the main sales KPI analysis until confirmed whether they represent returns or data errors.
- Rows missing required KPI fields or valid dates are excluded from the main analysis.

## Important result interpretation
The supplied workbook has 2,000 rows. Initial audit found 23 duplicate `Order_ID` rows, 24 dates that could not be parsed, 41 negative quantities, and missing values in several columns. After the documented deduplication and KPI filters, 1,836 rows were available for the main analysis in the current run. The notebook recomputes these counts when run.

This appears to be a practice dataset, so findings are illustrative and should not be presented as verified real-company results. Negative quantities may represent returns; confirm business meaning before making decisions.

## References
- pandas: https://pandas.pydata.org/docs/
- Matplotlib: https://matplotlib.org/stable/
- scikit-learn is not required for this descriptive analytics version.
