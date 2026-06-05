
# Clinical Hematology Data Workflow & Validation Project

## System Overview
This project simulates a structured data processing and validation workflow for clinical laboratory data.
The system is designed to:
- Ingest semi-structured hematology data from multiple files.
- Apply standardized cleaning and transformation rules.
- Validate data using rule-based logic.
- Output structured and categorized results for downstream analysis.

This workflow reflects common data handling processes in software systems, including ingestion, transformation, validation, and output generation.

---

## Project Context
This project focuses on the cleaning, transformation, and validation of raw hematology data exported from a URIT Auto Hematology Analyzer.
Approximately 150 complete hemograms were processed. The original exports were semi-structured and not analysis-ready. The objective was to design a structured workflow to standardize, validate, and summarize laboratory parameters using Microsoft Excel and Power Query.

This project is part of a professional portfolio demonstrating applied data analytics skills in a clinical laboratory context.

---

## Objectives
- Transform raw analyzer exports into structured datasets.
- Implement data cleaning and normalization procedures.
- Standardize numeric formats and handle non-numeric values.
- Apply rule-based validation for laboratory reference ranges.
- Generate parameter-level summary statistics (Average, Min, Max) using structured formulas.
- Demonstrate practical proficiency in Excel, Power Query, basic VBA automation, and relational logic.

---

## Tools & Technologies
- **Microsoft Excel** (Data modeling, formulas, and dashboards)
- **Power Query** (ETL - Extraction, Transformation, and Loading)
- **VBA / Macros** (Custom automation functions)
- **Conditional Logic & Statistical Aggregation Functions**
- *(Planned)* Power BI for visualization and analysis
- *(Planned)* Python (pandas) for automation and classification

---

## System Workflow

### 1) Data Ingestion
- Batch import of analyzer files from a folder.
- Combination of multiple files using Power Query.
- Selection of relevant worksheet pages.

### 2) Structural Cleaning (Power Query)
- Removal of header and footer rows.
- Elimination of non-informative rows.
- Filtering irrelevant columns.
- Header normalization.

### 3) Data Standardization & Modeling
- Cleaning whitespace and non-printable characters.
- Decimal normalization (conversion of separators).
- Numeric validation using logical checks.
- Handling invalid entries using controlled error logic.
- Conversion of the final output into an official **Excel Table** structure with the columns: `Patient_ID`, `Parameter`, `Result`, `Numeric_Value`, and `Status`.

### 4) Rule-Based Validation & Aggregation
Each hematological parameter was categorized based on predefined thresholds. Reference ranges were based on instrument-defined values.
- **Validation Logic:**
  - Non-numeric values → classified as `"NA"`
  - Values above defined range → `"HIGH"`
  - Values below defined range → `"LOW"`
  - Values within range → `"VALUE IN RANGE"`
- **Statistical Aggregation:**
  Conditional aggregation was implemented using structured Excel formulas (`PROMEDIO.SI.CONJUNTO`, `MAX.SI.CONJUNTO`, `MIN.SI.CONJUNTO`) to calculate Average, Maximum, and Minimum metrics while excluding `"NA"` values. Additionally, a fixed summary matrix using `CONTAR.SI` tracks the total volume of each validation status.

### 5) Interactive Analytics Layer (Dashboard)
To facilitate data review, an interactive reporting interface was built directly from the structured table:
- **Pivot Table:** Cross-references laboratory `Parameter` fields with their respective validation `Status`.
- **Dynamic Chart:** A clustered/stacked column chart visually maps the distribution of flags.
- **Slicers (Segmentators):** Two interactive slicers allow users to filter the entire dashboard by `PARAMETER` and `STATUS` with a single click.

### 6) Automation Layer (VBA Custom Function)
To complement the built-in validation, a custom User-Defined Function (UDF) was programmed in VBA to categorize sample magnitude into priority scales (`Alto`, `Medio`, `Bajo`), minimizing manual auditing steps.

vba
Function EvaluarCriticidad(valor As Double) As String
    ' Lógica adaptada: evalúa la magnitud del parámetro analizado
    If valor > 80 Then
        EvaluarCriticidad = "Alto"
    ElseIf valor >= 30 And valor <= 80 Then
        EvaluarCriticidad = "Medio"
    Else
        EvaluarCriticidad = "Bajo"
    End If
End Function 


## User Guide

### How to Use the Dataset 
1. Load the processed dataset in Excel (Data_Hematograma_2.xlsm).
2. Review the "Status" column to identify flags (VALUE IN RANGE, LOW, HIGH, NA).
3. Use the Dashboard tab to interact with the chart and filter parameters via Slicers.
4. Execute or review the custom VBA column (CRITIC_LEVEL) to check the calculated priority values.
5. Refer to summary tables for aggregated insights (average, min, max).
   
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

-Current Limitations: Manual Excel-based rule implementation (not yet fully automated), no biological reference validation, no species-level classification.

-No visualization layer yet implemented (Corrected in V02)

##Repository Structure

-📄 Data_Hematograma_2.xlsm -> Core data pipeline, BI Dashboard, and VBA macro script repository.
-📁 SQL_Bonus -> Contains an optimized relational database script (.sql) demonstrating table-joins (INNER JOIN) and categorical aggregation (GROUP BY) for a clinical operational test requirement.
-📄 README.md -> Project documentation.

## Project Roadmap

### Phase 2 – Python Implementation & Automation


---

## Project Status
**Work in Progress** – This repository is actively updated as new backend automation layers, database queries (`/SQL_Bonus`), and the upcoming Python processing pipeline are deployed.


