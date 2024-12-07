# Funding-analysis-of-Indian-Startups

OVERVIEW

This project focuses on two main components: cleaning and standardizing a dataset related to startup funding, and analyzing the funding landscape of Indian startups using Power BI. The primary goals are to ensure data integrity and provide insights into trends and patterns in the startup ecosystem.

INTRODUCTION

This repository contains SQL scripts for cleaning a startup funding dataset and Power BI files for analyzing and visualizing the funding landscape of Indian startups. The scripts ensure data integrity by removing duplicates, handling null values, and enhancing dataset usability through industry classification. The Power BI visualizations provide insights into trends and patterns in the startup ecosystem.

DATA CLEANING AND STANDARDIZATION

Removing Duplicates
1. Create a Staging Table: Create a staging table identical to the original dataset to work on the data without affecting the original.
2. Insert Data into Staging Table: Copy data from the original table to the staging table.
3. Identify and Remove Duplicates: Identify duplicate records using a Common Table Expression (CTE) with the ROW_NUMBER function and then remove them.

Standardizing Data
1. Rename Columns: Rename columns for consistency and to follow naming conventions.
2. Trim Whitespace: Remove leading and trailing whitespace in text fields.
3. Standardize Specific Values: Standardize common values (e.g., different spellings of startup names and city names).
   
Handling Null or Blank Values
1. Identify Null or Blank Values: Run queries to find records with null or blank values.
2. Update Null or Blank Values: Update these values to more meaningful default values or infer from other related records where possible.

Cleaning Up Specific Columns
1. Industry Column: Update missing values by inferring from other records with the same startup name.
2. SubVertical Column: Apply similar cleaning steps to the SubVertical column.
3. City Column: Standardize city names and correct common misspellings.
4. Investors and Investment Type Column: Remove unnecessary characters and standardize entries.
5. Date Column: Change the data type after correcting some of the values.

Special Handling of Amount_USD Column
1. Reduce Values Temporarily: Divide values in the Amount_USD column by 1000 to make them manageable.
2. Alter Column Type: Modify the column type to FLOAT.
3. Restore Original Values: Multiply the values back by 1000 to restore their original scale.

Industry Sector Classification
1. Industry Classification: Execute queries to categorize industries based on keywords related to sectors such as Food and Beverages, Agriculture, Automotive, Healthcare, Finance, Education, Hospitality, E-Commerce, Gaming, Transportation and Logistics, Fashion, Real Estate, Technology, Sustainability, and Services.
2. Handling Null or 'nan' Industries: Identify and update any industries marked as 'nan' or null to a more meaningful category ('Other').
3. Final Cleanup and Sector Assignment: Assign 'Other' to any remaining null sectors, review distinct sectors, and update the original funding dataset with the newly classified sectors.

INSIGHTS

The analysis provides several key insights, including:
1. Funding Growth: Understanding how startup funding has evolved over time.
2. Secotrs Hotspots: Identifying which sectors and sub-verticals are attracting the most funding.
3. City-Level Analysis: Discovering which cities are the major hubs for startup activity.
4. Investor Patterns: Analyzing the behavior and focus areas of key investors in the ecosystem.
5. Funding Rounds: Understanding the distribution and trends in different types of investment rounds.
