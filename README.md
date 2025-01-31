# Data-Cleaning and Exploratory Data Analysis(EDA) in MySQL
## Table of Contents

- [Project Overview](#project-overview)
- [Dataset Overview](#dataset-overview)
- [Common Issues Identified](#common-issues-identified)
- [Objectives](#objectives)
- [Tools](#tools)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Identifying Duplicate Rows](#identifying-duplicate-rows)
- [Results](#results)
- [Recommendations](#recommendations)

# Data Cleaning 🧹
## Project Overview
This project demonstrates how to clean and preprocess raw data using MySQL to ensure accuracy and reliability.Fixing issues in the raw data helps so that when you start creating visualizations the data is useful and there are no issues with it. The dataset contains data from the worlds layoffs of companies from 2020 to 2023.The goal is to identify and resolve common data quality issues such as missing values, duplicates, inconsistent formats and incorrect data types.

create a db
import a dataset
clean the data

## Dataset Overview
**Source** 
[Layoffs dataset](https://github.com/AlexTheAnalyst/MySQL-YouTube-Series/blob/main/layoffs.csv)

**Description** Contains company, location, industry, date, country and many more

## Common Issues Identified
- duplicates in the industry column
- Missing values in the industry column
- Null values in the dataset
- Incorrect data types such as date stored as text in the date column

## Objectives
- Remove duplicate rows
- Correct the incorrect data types
- Handle missing values effectively
- Standardize date format for consistency

## Tools 
**Database** MySQL

**IDE** MySQL Workbench

**SQL TECHNIQUES** UPDATE, DELETE, ALTER TABLE, JOIN

# Exploratory Data Analysis
EDA involved exploring the layoff dataset to answer questions such as :
1. When did the layoffs start?
2. Which countries had the most layoffs?
3. Which industry was mostly affected by the layoffs?
4. What was the total number of employees before the layoffs?

## Identifying Duplicate Rows
```sql
WITH duplicate_cte AS
(
SELECT * ,
ROW_NUMBER() OVER(
PARTITION BY company,location, industry,total_laid_off,percentage_laid_off, `date`,stage, country,funds_raised_millions) AS row_num
FROM layoff_staging
)
```

## Results 
After covid, a lot of companies were affected and have ended up letting go of a number of their employees. Some companies have completely gone under laying off all their employees. Some industries were affected more than others. 

## Recommendations 
1. Invest in innovation and market adaptability
2. Reskilling and Upskilling employees
3. Implementing flexible work models - introduce hybrid and remote work



