# **Exploratory Data Analysis for Norwegian "Catch Data" (Fangstdata) Datasets 2020-2024**

## Overview

This repository contains an exploratory data analysis (EDA) of Norwegian "Catch Data" (Fangstdata) for the years 2020-2024. The analysis was conducted using PySpark and pandas to handle large datasets efficiently. The primary goal of this analysis is to gain insights into fishing activities in Norway, including vessel operations, catch volumes, and economic data.

## Data Source

The data used in this project is sourced from the Norwegian Directorate of Fisheries (Fiskeridirektoratet), and involves the complete 'catch data' (Fangstdata) from the years 2020 - 2024. The datasets are licensed under the Norwegian License for Public Data (NLOD).

- **Source:** [Fiskeridirektoratet](https://www.fiskeridir.no/Tall-og-analyse/AApne-data/Fangstdata-seddel-koblet-med-fartoeydata)

## Libraries Used

- PySpark
- pandas
- matplotlib
- seaborn
- numpy

## Analysis Workflow

### 1. **Data Loading**
   - The datasets for each year (2020-2024) were loaded using PySpark for efficient handling of large files. A custom schema was defined to ensure correct data types during the import process.

### 2. **Data Cleaning**
   - **Duplicate Removal**: Duplicates were identified and removed.
   - **Whitespace Trimming**: Whitespace was trimmed from string columns.
   - **Type Conversion**: Key columns such as `Fangstverdi` (Total Revenue) and `Rundvekt` (Total Weight) were converted from strings to numerical/double types.
   - **Handling Null Values**: Columns with significant null values were either cleaned or dropped based on relevance to the analysis.

### 3. **Exploratory Data Analysis**
   - **Data Exploration**: Initial exploration involved checking distinct values for key columns, such as fishing equipment (`Redskap`) and species of fish (`Art FAO`).
   - **Column Selection**: Relevant columns were selected for further analysis, focusing on vessel information, catch data, and economic metrics.
   - **Municipality Focus on Herøy kommune**: The analysis was particularly focused on vessels registered in Herøy kommune, investigating their activity and catch patterns.

### 4. **Data Analysis Questions**
   - **Area-Based Analysis**: Which areas (`Hovedområde`) see the most fishing activity?
   - **Time-Based Trends**: Analysis of catch volume (`Rundvekt`) and revenue across different months and years.
   - **Revenue & Weight Correlation**: Examining the relationship between the amount of fish caught and the revenue generated.
   - **Fish Species Analysis**: Identifying which vessels catch the most of each species and analyzing price variations.

### 5. **Vessel Information Table**
   - A comprehensive table of vessel information was created, detailing attributes such as vessel type, build year, engine power, and the fishing equipment used.

## Key Findings

- The dataset contains **4,932,203 rows and 133 columns** after combining and cleaning the data from 2020 to 2024.
- A total of **133 unique fish species** were identified, with specific focus on high-value species and their corresponding catch volumes.
- The analysis highlights significant regional and temporal variations in fishing activity and revenue.

## Insights & Future prospects Regarding Libraries and Project Structure
- In order to save files for this project I was limited by the amount of data pandas could handle, as PySpark DataFrames had to be converted to pandas DataFrames. 
   
   - PySpark requires a HADOOP installation, which can be quite tedious to set up for a simple home-based project.

- I would have instead used Polars & Dask, in combination with pandas, to handle the data for this project. This would allow to save DataFrames more easily.
- For this specific project, a lot of the data was filtered on a scale that pandas could handle, so it worked out well. However, for future projects where I want to save more files earlier on in the process prior to filtering and selecting, I will go with Dask.
