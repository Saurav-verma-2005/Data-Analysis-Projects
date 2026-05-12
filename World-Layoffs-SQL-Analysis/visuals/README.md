# World Layoffs Data Cleaning & EDA 📉

## Project Overview
This project involves a comprehensive data cleaning process and exploratory data analysis (EDA) of a global layoffs dataset. The goal was to transform "messy" raw data into a structured format suitable for analysis and then uncover trends regarding which industries and countries were hardest hit by layoffs between 2020 and 2023.

## Dataset
- **Source:** Kaggle 
- **Format:** CSV
- **Size:** 2,300+ rows of data including company, location, industry, total laid off, date, and funding stage.

## Part 1: Data Cleaning
The raw data was initially loaded into MySQL. The cleaning process involved:
1. **Duplicate Removal:** Used `ROW_NUMBER()` and `CTE`s to identify and delete duplicate entries.
2. **Standardization:** - Trimmed whitespace from company names.
   - Standardized industry names (e.g., merging various 'Crypto' labels).
   - Fixed trailing punctuation in country names (e.g., 'United States.').
3. **Date Conversion:** Converted the `date` column from a string format to a proper SQL `DATE` type.
4. **Handling Nulls:** Populated missing industry values by joining the table to itself where data was available in other rows for the same company.
5. **Data Removal:** Dropped unnecessary columns and rows with insufficient data (nulls in both total and percentage laid off).

## Part 2: Exploratory Data Analysis (EDA)
With a clean dataset, I performed several queries to extract insights:
- **Major Players:** Identified companies like Amazon, Google, and Meta with the highest total layoffs.
- **Industry Impact:** Analyzed which sectors (Consumer, Retail, Transportation) saw the most significant job cuts.
- **Temporal Trends:** - Calculated total layoffs per year (showing the 2022-2023 spike).
    - Created a **Rolling Total of Layoffs** by month to visualize the progression of job cuts over time.
- **Geography:** Ranked countries by total layoffs, with the United States and India appearing prominently.

## Tools Used
- **Database:** MySQL
- **Skills:** Common Table Expressions (CTEs), Window Functions, Joins, Data Type Casting, Aggregate Functions.

## How to Use
1. Run the `01_data_cleaning.sql` script to set up the staging tables and clean the data.
2. Run the `02_exploratory_analysis.sql` script to view the insights.
