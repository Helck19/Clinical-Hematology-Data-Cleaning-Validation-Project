# Clinical-Hematology-Data-Cleaning-Validation-Project

This project focuses on the cleaning, transformation, and validation of raw hematology data exported from a URIT Auto Hematology Analyzer.

Approximately 150 complete hemograms were processed. The original exports were semi-structured and not analysis-ready. The objective was to design a structured workflow to standardize, validate, and summarize laboratory parameters using Microsoft Excel and Power Query.

This project is part of a professional portfolio demonstrating applied data analytics skills in a clinical laboratory context.

# Objectives
-Transform raw analyzer exports into structured datasets

-Implement data cleaning and normalization procedures

-Standardize numeric formats and handle non-numeric values

-Apply rule-based validation for laboratory reference ranges

-Generate parameter-level summary statistics (Average, Min, Max)

-Demonstrate practical proficiency in Excel and Power Query

# Tools & Technologies
-Microsoft Excel

-Power Query

-Conditional Logic & Statistical Aggregation Functions

-(Planned) Power BI for visualization and analysis

-(Planned) Python (pandas) for automation and classification

# Data Processing Workflow

1) Data Ingestion

-Batch import of analyzer files from folder

-Combination of multiple files using Power Query

-Selection of relevant worksheet pages

2) Structural Cleaning

-Removal of header and footer rows

-Elimination of non-informative rows

-Filtering irrelevant columns

-Header normalization
3) Data Standardization

-Cleaning whitespace and non-printable characters

-Decimal normalization (conversion of separators)

-Numeric validation using logical checks

-Handling invalid entries using controlled error logic
4) Rule-Based Validation
Each hematological parameter was categorized into:

-LOW

-HIGH

-VALUE IN RANGE

-NA (non-numeric or invalid entry)

Reference ranges were based on instrument-defined values.

Conditional formatting was applied to visually flag abnormal results.

# Statistical Aggregation

For each parameter, the following metrics were calculated:

-Average (excluding invalid entries)

-Maximum (excluding invalid entries)

-Minimum (excluding invalid entries)

Conditional aggregation was implemented using structured Excel formulas (PROMEDIO.SI.CONJUNTO, MAX.SI.CONJUNTO, MIN.SI.CONJUNTO) to exclude "NA" values.

# Key Skills Demonstrated

-Batch data ingestion

-Data cleaning and preprocessing

-Rule-based validation systems

-Structured aggregation logic

-Conditional filtering

-Clinical data interpretation awareness

-Analytical workflow design

# Important Considerations

-No species stratification (cats vs dogs) was applied in this phase.

-Reference ranges were instrument-defined and not species-adjusted.

-The primary goal of this phase was data cleaning, validation, and standardization — not clinical interpretation.

# Current Limitations

-Manual Excel-based rule implementation (not yet fully automated)

-No biological reference validation

-No species-level classification

-No visualization layer yet implemented

# Project Roadmap

Phase 2 – Power BI Integration

* Dashboard visualization of parameter distributions

* Out-of-range frequency analysis

* Comparative parameter trends

Phase 3 – Python Implementation

* Migration of cleaning and validation pipeline to pandas

* Automated rule engine

* Species classification modeling

* Reproducible data pipeline

Status

# Work in Progress – This repository will be continuously updated as new analytical layers (Power BI, Python automation, classification modeling) are implemented.
