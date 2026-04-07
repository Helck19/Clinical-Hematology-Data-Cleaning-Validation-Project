# Clinical Data Workflow & Validation Project

## System Overview

This project simulates a structured data processing and validation workflow for clinical laboratory data.

The system is designed to:
- Ingest semi-structured hematology data from multiple files
- Apply standardized cleaning and transformation rules
- Validate data using rule-based logic
- Output structured and categorized results for downstream analysis

This workflow reflects common data handling processes in software systems, including ingestion, transformation, validation, and output generation.

## Project context

This project focuses on the cleaning, transformation, and validation of raw hematology data exported from a URIT Auto Hematology Analyzer.

Approximately 150 complete hemograms were processed. The original exports were semi-structured and not analysis-ready. The objective was to design a structured workflow to standardize, validate, and summarize laboratory parameters using Microsoft Excel and Power Query.

This project is part of a professional portfolio demonstrating applied data analytics skills in a clinical laboratory context.

### Objectives
-Transform raw analyzer exports into structured datasets

-Implement data cleaning and normalization procedures

-Standardize numeric formats and handle non-numeric values

-Apply rule-based validation for laboratory reference ranges

-Generate parameter-level summary statistics (Average, Min, Max)

-Demonstrate practical proficiency in Excel and Power Query

### Tools & Technologies
-Microsoft Excel

-Power Query

-Conditional Logic & Statistical Aggregation Functions

-(Planned) Power BI for visualization and analysis

-(Planned) Python (pandas) for automation and classification

## System Workflow

### 1) Data Ingestion

-Batch import of analyzer files from folder

-Combination of multiple files using Power Query

-Selection of relevant worksheet pages

### 2) Structural Cleaning

-Removal of header and footer rows

-Elimination of non-informative rows

-Filtering irrelevant columns

-Header normalization

### 3) Data Standardization

-Cleaning whitespace and non-printable characters

-Decimal normalization (conversion of separators)

-Numeric validation using logical checks

-Handling invalid entries using controlled error logic

### 4) Rule-Based Validation

Each hematological parameter was categorized based on predefined thresholds.

Reference ranges were based on instrument-defined values.

Conditional formatting was applied to visually flag abnormal results.

## Validation Logic

Validation rules were applied to ensure data consistency and reliability: 

- Non-numeric values → classified as "NA"
- Values above defined range → "HIGH"
- Values below defined range → "LOW"
- Values within range → "VALUE IN RANGE"

These rules simulate validation logic commonly used in software systems to detect inconsistencies, edge cases, and invalid inputs.

## Statistical Aggregation

For each parameter, the following metrics were calculated:

-Average (excluding invalid entries)

-Maximum (excluding invalid entries)

-Minimum (excluding invalid entries)

Conditional aggregation was implemented using structured Excel formulas (PROMEDIO.SI.CONJUNTO, MAX.SI.CONJUNTO, MIN.SI.CONJUNTO) to exclude "NA" values.

## Key Skills Demonstrated

-Batch data ingestion

-Data cleaning and preprocessing

-Rule-based validation systems

-Structured aggregation logic

-Conditional filtering

-Clinical data interpretation awareness

-Analytical workflow design

## User Guide

### How to Use the Dataset 
1. Load the processed dataset in Excel
2. Review the "success" column:
    - "VALUE IN RANGE" → normal values 
    - "LOW" / "HIGH" → flagged values
    - "NA" → invalid or missing data
4. Use conditional formatting to quickly identify abnormal parameters
5. Refer to summary tables for aggregated insights (average, min, max)

### Intended Use 
This dataset is intended for: 
- Data validation analysis
- Quality checks
- Exploratory analysis of hematological parameters

## Important Considerations

-No species stratification (cats vs dogs) was applied in this phase.

-Reference ranges were instrument-defined and not species-adjusted.

-The primary goal of this phase was data cleaning, validation, and standardization — not clinical interpretation.

## Current Limitations

-Manual Excel-based rule implementation (not yet fully automated)

-No biological reference validation

-No species-level classification

-No visualization layer yet implemented


## Project Roadmap

Phase 2 – Power BI Integration

* Dashboard visualization of parameter distributions

* Out-of-range frequency analysis

* Comparative parameter trends

Phase 3 – Python Implementation

* Migration of cleaning and validation pipeline to pandas

* Automated rule engine

* Species classification modeling

* Reproducible data pipeline

## Project Status

# Work in Progress – This repository will be continuously updated as new analytical layers (Power BI, Python automation, classification modeling) are implemented.
