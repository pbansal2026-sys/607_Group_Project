# Public vs Private Firm Size in Singapore

A DS607: Data Science for Economics group project comparing the financial size of publicly listed and privately held Singaporean companies from 2021 to 2025.

## Project motivation

Public and private companies may differ substantially in scale, access to capital, and financial structure. This project examines whether their revenue and total-asset distributions differ in Singapore and estimates the size of the annual gap between the two groups.

## Research question

Do the operating revenue and total-asset distributions of public and private Singaporean companies differ from 2021 to 2025?

For each year and financial measure, we estimate the difference between the public and private median and construct a 95% bootstrap confidence interval.

## Group members

- Madhurima S Rudra
- Nehantha Sathesh
- Paavas Bansal

## Data source

The project uses company-level data from the Orbis database. The analysis focuses on:

- Operating revenue (turnover)
- Total assets
- Singaporean companies
- Years 2021 to 2025
- Listed and unlisted companies

## Getting the data

```mermaid
flowchart TD
    A["Location filter: Singapore"] --> B["Only active firms"]
    B --> C["Key financials"]
    C --> D["Operating revenue (Turnover)<br/>absolute, USD million, 2021 to 2025"]
    D --> E["Total assets<br/>absolute, USD million, 2021 to 2025"]
    E --> F["Consolidation code"]
    F --> G["Listing status"]
    G --> H["Export to Excel (.xlsx)"]
    H --> I["Save as data_million_.xlsx"]
```

## Running the project

1. Create and activate a Python environment.
2. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Place the raw dataset in `data/raw/`.
4. Run `notebooks/Wrangle_&_Tests.ipynb` to clean the data, run the statistical tests, and create the processed data and output files described above.

## Data availability

The `data/raw/` and `data/processed/` folders are excluded from Git. This is to prevent uploading licensed ORBIS data into a public platform.


## Method

The analysis proceeds as follows:

1. Clean the company-level financial data and document missing, zero, and negative values.
2. Keep Singaporean firms classified as listed or unlisted.
3. Reshape the source data into a company-year dataset.
4. Generate descriptive tables, ECDF and box plots for each public and private financial measure.
5. Run two-sample Kolmogorov-Smirnov tests to assess whether the public and private financial distributions differ.
6. Calculate annual public-minus-private median differences.
7. Use bootstrap resampling with a fixed random seed to construct 95% confidence intervals for the median differences.


## Outputs

The project produces:

- Descriptive statistics showing usable sample sizes and annual medians by group
- KS test statistics and p-values for revenue and total assets
- KS statistic (D) trend by year for revenue and total assets
- Annual median differences with 95% bootstrap confidence intervals
- Distribution plots for public and private firms
- Line charts of annual group medians
- Confidence-interval plots of annual median differences
- Final project presentation in [`outputs/presentation/final_presentation.pdf`](outputs/presentation/final_presentation.pdf)

## Repository structure

```text
.
|-- notebooks/
|   `-- Wrangle_&_Tests.ipynb   # Data cleaning, tests, and output generation
|
|-- data/
|   |-- raw/                    # Original ORBIS Excel files; excluded from Git
|   |   |-- companies_orbis_results.xlsx
|   |   `-- data_million_.xlsx
|   `-- processed/              # Cleaned data and analysis tables; excluded from Git
|       |-- companies_cleaned_wide.csv
|       |-- company_year_panel.csv
|       |-- ks_table.csv
|       `-- boot_table.csv
|
|-- outputs/
|   |-- figures/                # Report-ready charts
|   |   |-- ecdf_revenue.png
|   |   |-- ecdf_total_assets.png
|   |   |-- eda_boxplots_by_year_group.png
|   |   |-- ks_ecdf_gap.png
|   |   |-- ks_statistic_by_year.png
|   |   |-- median_difference_confidence_intervals.png
|   |   `-- median_line_charts(log).png
|   `-- tables/                 # Report-ready statistical tables
|       `-- descriptive_statistics.csv
|   `-- presentation/          # Final project presentation
|       `-- final_presentation.pdf
|
|-- requirements.txt            # Python package requirements
|-- AI_USAGE.md                 # Declaration of generative-AI use
|-- CONTRIBUTIONS.md            # Group-member contributions
|-- .gitignore
`-- README.md
```
## Reproducibility

Bootstrap resampling uses a fixed random seed so that results can be reproduced when the same input data and code are used.

## AI use and contributions

See [AI_USAGE.md](AI_USAGE.md) for the group’s generative-AI declaration and [CONTRIBUTIONS.md](CONTRIBUTIONS.md) for individual contributions.
