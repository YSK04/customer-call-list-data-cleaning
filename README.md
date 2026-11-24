# Customer Call List Data Cleaning (Pandas)

A Python data cleaning workflow using `pandas` to standardize and structure a raw customer call list dataset for downstream processing and analysis.

## Overview
The dataset includes customer contact fields (`CustomerID`, `First_Name`, `Last_Name`, `Phone_Number`, `Address`, `Paying Customer`, `Do_Not_Contact`, and `Not_Useful_Column`) containing duplicate records, formatting variations, missing values, and non-contactable rows. Sample dataset initialization is embedded directly inside the notebook so the workflow can execute standalone without an external file.

## Cleaning Workflow
- **Duplicate Removal & Column Filtering:** Drops duplicate entries and removes `Not_Useful_Column`.
- **Name Field Cleanup:** Strips leading and trailing characters (`123._/`) from `Last_Name`[cite: 9].
- **Phone Number Standardization:** Extracts digits using regular expressions, formats 10-digit numbers into `XXX-XXX-XXXX`, and normalizes missing or invalid values (`N/a`, `NaN`, `None`) to empty strings[cite: 9].
- **Status Normalization & Filtering:** Standardizes `Yes`/`No` values to `Y`/`N` across `Paying Customer` and `Do_Not_Contact`, and excludes records where `Do_Not_Contact` is `'Y'` or empty[cite: 9].
- **Address Decomposition:** Splits `Address` into `Street_Address`, `State`, and `Zip_Code` columns[cite: 9].

## Repository Contents
```text
customer-call-list-data-cleaning/
├── customer_data_cleaning.ipynb
└── README.md
