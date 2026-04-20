# HR Data Integrity Audit & Performance Standardization

## Project Overview
This project focuses on auditing and cleaning a fragmented HR dataset containing 550 employee records. The primary objective was to resolve "Data Decay" and structural inconsistencies to enable reliable HR analytics, such as attrition modeling and payroll reviews.

##  The Data Challenge
The raw dataset was plagued by high levels of categorical noise and formatting errors that would break standard BI tools (Power BI/Tableau):
- **Categorical Noise:** 47 inconsistent department variations and 41 job role titles.
- **Encoding Issues:** Identified "lookalike" Unicode characters (e.g., Cyrillic 'а') that caused duplicate grouping errors.
- **Temporal Inconsistency:** 7+ different date formats (e.g., `DD.MM.YYYY`, `MM-DD-YYYY`, `Month DD, YYYY`).
- **Financial Format Decay:** Mixed currency symbols (₦, NGN, N) and non-numeric strings in salary fields.

##  Technical Solutions
Using **Python (Pandas)**, I implemented a repeatable cleaning pipeline:
1. **Unicode Normalization:** Applied `unicodedata` NFKC normalization to resolve character encoding conflicts.
2. **Standardized Mapping:** Developed a dictionary-based mapping logic to reduce Department noise by **83%** (from 47 to 8 core categories).
3. **Date Uniformity:** Parsed multi-format strings into the global **ISO 8601 (YYYY-MM-DD)** standard.
4. **Logic Auditing:** Standardized "Promotion Status" and "Exit Status" into boolean-friendly categories for machine learning readiness.

##  Business Impact
- **Accuracy:** Achieved 100% data integrity across salary and tenure fields.
- **Interoperability:** The final output is optimized for SQL injection and Power BI dashboarding.
- **Audit Ready:** Corrected logical inconsistencies (e.g., employees marked as "Promoted" with failing performance scores).

## Repository Structure
- `data/`: Contains raw and standardized CSV samples.
- `scripts/`: Python cleaning script (`hr_audit_clean.py`).
- `notebooks/`: Exploratory Data Analysis (EDA) of the audit process.

---
##  How to Reproduce
1. Clone this repository: `git clone https://github.com/your-username/HR-Data-Standardization-Audit.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Run the audit script: `python scripts/hr_audit_clean.py`
4. View the results in `data/standardized_hr_data.csv`

**Author:** Oluwasegun Kamikun Rolland  
**Role:** Data Quality Specialist | Economics Graduate
