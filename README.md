# UVA Medical Center Quality & Performance Benchmarking

## Project Overview

This project evaluates UVA Medical Center against other Virginia hospitals using publicly available Centers for Medicare & Medicaid Services (CMS) hospital quality data.

The analysis combines multiple CMS datasets, standardizes hospital identifiers and quality measures, builds a Virginia peer benchmark, and compares UVA across selected measures in four quality categories:

• Timely Care
• Readmissions
• Healthcare-Associated Infections
• Mortality & Complications

Because the selected measures use different units and scales, the project uses direction-adjusted z-scores to make cross-measure comparisons more meaningful. UVA is excluded from its own peer benchmark calculations.

The project was completed using Python, SQL, and Power BI.

────────

## Business Question

How does UVA Medical Center perform across selected CMS quality measures compared with other Virginia hospitals?

Supporting questions include:

• Which measures show UVA performing more favorably than Virginia peers?
• Which measures show the largest unfavorable benchmark gaps?
• How does performance differ across major quality categories?
• Can measures with different units be compared on a standardized scale?

────────

## Data Sources

Five public CMS hospital datasets were used:

1. Hospital General Information
2. Timely & Effective Care
3. Unplanned Hospital Visits
4. Healthcare-Associated Infections
5. Complications & Mortality

## Primary key: Facility ID

UVA Medical Center CMS Facility ID: 490009

The original CMS data is national. The analysis narrows the comparison population to Virginia hospitals.

────────

##Tools Used

• Python
  • Pandas
  • NumPy
• SQL
  • SQLite
  • CTEs
  • JOINs
  • CASE statements
  • Aggregate functions
  • Window functions
• Power BI
  • DAX
  • KPI cards
  • Slicers
  • Benchmark visualizations
• Google Colab
• GitHub

────────

## Project Workflow

### 1. Data Loading and Validation

The five CMS datasets were loaded into Python and reviewed for:

• shape and structure
• column consistency
• missing values
• data types
• Facility ID formatting
• UVA record availability

Facility IDs were standardized as six-character text values so hospitals could be matched reliably across datasets.

### 2. Data Cleaning

The cleaning process included:

• converting CMS text-based missing values to null values
• standardizing Facility IDs
• converting quality scores to numeric values
• converting date columns to datetime
• removing exact duplicates
• preserving legitimate repeated hospital-measure records
• filtering quality datasets to Virginia hospitals

### 3. Measure Selection

Twelve CMS quality measures were selected across four categories.

The project focuses on a smaller set of measures to make the analysis interpretable while still covering multiple areas of hospital quality.

Examples include measures related to:

• emergency department timeliness
• safe opioid use
• unplanned visits
• heart failure readmissions
• hospital admissions after outpatient chemotherapy
• CLABSI and CAUTI infection ratios
• surgical-site infections
• stroke mortality
• surgical mortality
• inpatient fall-associated fractures

### 4. Virginia Peer Benchmarking

UVA Medical Center was separated from the peer population.

For each selected measure, the project calculates:

• Virginia peer mean
• Virginia peer median
• Virginia peer standard deviation
• peer hospital count
• UVA score
• raw benchmark difference
• performance direction
• direction-adjusted benchmark gap
• raw z-score
• direction-adjusted z-score
• benchmark status

UVA is excluded from its own peer benchmark calculations.

### 5. Standardized Performance Analysis

CMS measures use different units such as:

• minutes
• rates
• percentages
• standardized infection ratios

Because raw differences are not directly comparable across these scales, z-scores were used to standardize UVA’s distance from the Virginia peer average.

Performance direction was then incorporated so that:

• Positive direction-adjusted z-score = more favorable relative performance
• Negative direction-adjusted z-score = less favorable relative performance

This creates a consistent interpretation across the selected measures.

### 6. SQL Analysis

The cleaned analytical dataset was loaded into SQLite.

SQL was used to demonstrate:

• filtering
• aggregation
• grouping
• hospital-to-quality joins
• CASE logic
• Common Table Expressions
• window functions
• benchmark comparisons
• join-integrity validation
• z-score calculations
• direction-adjusted performance classification

### 7. Power BI Dashboard

## The final Power BI report contains two pages.

### Page 1: Executive Overview
<img width="603" height="339" alt="UVA Medical Center Quality   Performance Benchmarking" src="https://github.com/user-attachments/assets/ee8d4c3b-6868-4229-9927-5ff50fa4d098" />

Includes:

• number of selected UVA measures
• number of Virginia peer hospitals
• measures performing better or worse than the peer benchmark
• average direction-adjusted z-score by quality category
• interactive measure and category filters

### Page 2: Measure-Level Benchmark Analysis
<img width="598" height="338" alt="UVA Medical Center Measure Level Benchmark Analysis" src="https://github.com/user-attachments/assets/3ca6326d-4f02-4cd9-8a64-f2a2a4e98156" />

Includes:

• detailed UVA vs Virginia peer comparison table
• benchmark status
• direction-adjusted z-scores
• standardized benchmark-gap visualization
• methodology note explaining the benchmark approach

────────

## Key Findings

The analysis shows that UVA Medical Center does not follow a single performance pattern across all selected quality measures.

• UVA performs more favorably than the Virginia peer benchmark on some measures.
• Other measures show meaningful unfavorable standardized gaps.
• Performance varies across Timely Care, Readmissions, Infections, and Mortality & Complications.
• Measure-level benchmarking provides more useful detail than combining unrelated quality measures into one overall score.

The Power BI dashboard currently summarizes 12 selected measures across 86 Virginia peer hospitals.

────────

## Dashboard Methodology

UVA Medical Center is compared with other Virginia hospitals using selected CMS quality measures.

UVA is excluded from peer benchmark calculations. Because measures use different units and definitions, performance direction and standardized z-scores are used to make comparisons more consistent.

Positive direction-adjusted z-scores represent more favorable performance relative to Virginia peers, while negative values represent less favorable performance.

##How to Run the Analysis

1. Download the required CMS hospital datasets.
2. Open the notebook in Google Colab or Jupyter.
3. Upload the five source CSV files.
4. Run the notebook from top to bottom.
5. The notebook will clean the data, create the Virginia comparison population, calculate benchmarks, perform SQL analysis, and export analysis-ready files.
6. Load the cleaned outputs into Power BI to reproduce the dashboard.

────────

## Limitations

• The analysis uses a selected subset of CMS measures rather than every available hospital-quality measure.
• Not every Virginia hospital reports every selected measure.
• Peer benchmarking is limited to Virginia hospitals and does not control for differences in hospital size, teaching status, patient complexity, or service mix.
• Results reflect the reporting period contained in the downloaded CMS datasets and should not be interpreted as a complete measure of hospital quality.

────────

## Skills Demonstrated

• Multi-table data cleaning
• Data validation
• Relational keys and joins
• Missing-value handling
• Long-format healthcare data
• Benchmark construction
• Peer-group analysis
• Statistical standardization
• Z-score interpretation
• SQL querying
• CTEs and window functions
• Data-quality validation
• DAX
• Power BI dashboard design
• Data storytelling
• Technical documentation

────────

### Author

Syeda Tasnim Hossain

Data Analytics Portfolio Project
