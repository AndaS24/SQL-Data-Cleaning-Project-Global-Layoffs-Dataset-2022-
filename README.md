# SQL-Data-Cleaning-Project-Global-Layoffs-Dataset-2022-
SQL Data Cleaning Project: Global Layoffs Dataset (2022)

Overview:
This project focuses on cleaning and preparing the Layoffs 2022 dataset using SQL. The dataset contains real-world data on global layoffs across various industries and companies during 2022. The goal was to transform the raw, messy data into a clean and consistent format, ready for analysis or further processing.

Tools & Skills Used:
SQL (MySQL)
Data Cleaning Techniques
Window Functions (ROW_NUMBER())
CTEs (Common Table Expressions)
String and Date Manipulation
NULL Handling & Deduplication

Cleaning Steps
1. Create a Staging Table
A duplicate of the original dataset was created (layoffs_staging) to preserve raw data and allow flexible, safe transformations.

2. Remove Duplicates
Applied ROW_NUMBER() to identify duplicate rows based on multiple key columns.
Deleted rows with a row number greater than 1 (true duplicates).

3. Standardize and Fix Data
Converted blank fields to NULL for consistency.
Unified inconsistent entries (e.g., CryptoCurrency, Crypto Currency → Crypto).
Trimmed country names (e.g., removed trailing periods in United States.).
Converted date strings to SQL DATE format using STR_TO_DATE().

4. Handle Missing Values
Used JOIN logic to fill in missing industry values where other entries for the same company had this info.
Retained missing values in numeric fields (total_laid_off, percentage_laid_off) for accurate statistical handling later.

5. Remove Irrelevant Data
Dropped rows where both total_laid_off and percentage_laid_off were NULL.
Removed helper columns (e.g., row_num) used during cleaning.

Final Output
A fully cleaned SQL table (layoffs_staging2) ready for:
Exploratory Data Analysis (EDA)
Data Visualization
Reporting & Insights

Dataset Source
Kaggle - Layoffs 2022
