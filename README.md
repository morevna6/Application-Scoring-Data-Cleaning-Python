# Application Scoring and Data Cleaning

## Project Overview

This project focuses on cleaning application data, enriching it with industry scores, and calculating an application score based on predefined business rules.

The goal is to identify accepted applications and analyze the weekly average score of accepted applicants.

## Datasets

The project uses two datasets:

- `applications.csv`: Contains applicant information such as age, application date, amount, marital status, location, education level, industry, and external rating.
- `industries.csv`: Contains industry scores used as part of the application scoring logic.

## Tasks Completed

- Loaded the applications dataset into a Pandas DataFrame.
- Removed duplicate applicants based on `applicant_id`.
- Filled missing values in `External Rating` with 0.
- Filled missing or invalid values in `Education level` with `"Ortaokul"`.
- Merged application data with industry score data.
- Calculated an application score based on six business rules.
- Set the application score to 0 if `Amount` was missing or `External Rating` was 0.
- Filtered only accepted applications with a score greater than 0.
- Grouped accepted applications by application week.
- Visualized the weekly average application score.

## Scoring Logic

The application score is calculated based on the following rules:

- Age between 35 and 55: +20 points
- Application submitted on a weekday: +20 points
- Applicant is married: +20 points
- Applicant is located in Kyiv or nearby region: +10 points
- Industry score: 0 to 20 points
- External Rating is 7 or higher: +20 points
- External Rating is 2 or lower: -20 points

The final score is clipped between 0 and 100.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Key Output

The final analysis shows the average application score of accepted applications by week and year.

This helps evaluate how the quality of accepted applications changes over time.

## Project File

The main analysis is available in:

`application_scoring_analysis.ipynb`
