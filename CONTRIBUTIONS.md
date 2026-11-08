## Intro
This document summarises each team member’s primary contributions to the project.

The contributions below outline each member’s main contributions, but the project was completed collaboratively, with all members providing feedback and support across different stages of the work. Analytical decisions and any differences in approach were discussed and resolved jointly by the group.

### Madhurima Subramaniam Rudra
- Collected firm-level operating-revenue and total-assets data for Singaporean public and private companies from the Orbis database for 2021–2025.
- Cleaned and formatted the Orbis extract for analysis, including handling missing values and standardising revenue and total-assets fields across 2021-2025.
- Generated descriptive summary statistics, including medians and interquartile ranges, and produced box plots.
- Conducted annual two-sample Kolmogorov–Smirnov tests for operating revenue and total assets for each year, reporting the KS statistics and p-values.
- Computed bootstrap confidence intervals for annual public-private median differences between public and private firms, using a fixed random seed to ensure reproducibility.

### Paavas Bansal
- Managed the project’s GitHub repository, maintaining a clear repository structure, coordinating version control, resolving merge conflicts, keeping README.md up to date and keeping project dependencies documented in `requirements.txt`.
- Contributed to the initial exploration and assessment of the dataset before the final Orbis extract was selected.
- Strengthened the analytical rigor of the data-wrangling methodology by ensuring that the treatment of missing observations and the standardisation of financial measures supported valid, consistent comparisons between public and private firms.
- Produced the initial descriptive summary table.
- Generated the project’s analytical figures, including empirical cumulative distribution function (ECDF) curves, annual median plots, and public-private median-difference plots with bootstrap confidence intervals.

### Nehantha Sathesh