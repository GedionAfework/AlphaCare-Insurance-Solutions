# ACIS Car Insurance Analytics

## Overview

This repository contains the data analytics pipeline for AlphaCare Insurance Solutions (ACIS) to optimize car insurance marketing strategies in South Africa. The project analyzes historical insurance claim data (`MachineLearningRating_v3.txt`) to identify low-risk customer segments, enabling reduced premiums to attract new clients. The pipeline includes Exploratory Data Analysis (EDA), data version control with DVC, and a CI/CD workflow using GitHub Actions.

## Objectives

- Perform Exploratory Data Analysis (EDA) to uncover patterns in risk and profitability, focusing on:
  - Loss Ratio (TotalClaims / TotalPremium) by Province, VehicleType, and Gender.
  - Distributions and outliers in financial variables (e.g., TotalPremium, TotalClaims).
  - Temporal trends in claim frequency and severity.
  - Vehicle makes/models with high/low claim amounts.
- Establish a reproducible and auditable data pipeline using Data Version Control (DVC) for regulatory compliance.
- Optimize marketing strategies by identifying low-risk targets for premium reductions.

## Repository Structure

```
AlphaCare-Insurance-Solutions/
├── data/
│   └── MachineLearningRating_v3.txt  # Dataset (tracked by DVC)
├── notebooks/
│   └── eda.ipynb  # Jupyter notebook for EDA
├── plots/
│   └── *.png  # Generated EDA visualizations
├── scripts/
│   └── (placeholder for future scripts)
├── .dvc/
│   └── (DVC configuration and cache)
├── .github/
│   └── workflows/
│       └── ci.yml  # GitHub Actions CI pipeline
├── venv/
│   └── (virtual environment, ignored by Git)
├── .gitignore
├── README.md
├── requirements.txt  # Python dependencies
```

## Setup Instructions

1. **Clone the Repository**:

   ```bash
   git clone `https://github.com/GedionAfework/AlphaCare-Insurance-Solutions.git`
   cd acis_car_insurance_analytics
   ```

2. **Set Up Virtual Environment**:

   - Create and activate a virtual environment:
     ```bash
     python -m venv venv
     ```
     - Windows:
       ```bash
       .\venv\Scripts\activate
       ```
     - macOS/Linux:
       ```bash
       source venv/bin/activate
       ```

3. **Install Dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

4. **Initialize DVC**:

   - Initialize DVC and configure local storage:
     ```bash
     dvc init
     mkdir /path/to/local/storage
     dvc remote add -d localstorage /path/to/local/storage
     ```
   - Pull the dataset (if tracked by DVC):
     ```bash
     dvc pull
     ```

5. **Run EDA**:
   - Launch Jupyter Notebook:
     ```bash
     jupyter notebook
     ```
   - Open `notebooks/eda.ipynb` and run all cells to perform EDA and generate plots in the `plots/` directory.

## Usage

- **EDA**: The `notebooks/eda.ipynb` notebook loads `data/MachineLearningRating_v3.txt` and generates visualizations (e.g., histograms, heatmaps, pair plots) to analyze risk and profitability. Key insights include Loss Ratio variations, outliers, and temporal trends.
- **DVC**: The dataset is tracked with DVC for reproducibility. Use `dvc add`, `dvc push`, and `dvc pull` to manage data versions.
- **CI/CD**: GitHub Actions (`./github/workflows/ci.yml`) runs linting and placeholder tests on pushes and pull requests to `main` and `task-*` branches.

## Tasks Completed

- **Task 1: Git and GitHub Setup**:
  - Initialized Git repository with branches `main`, `task-1` (EDA), and `task-2` (DVC).
  - Configured GitHub Actions for CI/CD.
  - Created `notebooks/eda.ipynb` for EDA with seven visualizations.
- **Task 2: Data Pipeline with DVC**:
  - Initialized DVC and configured local storage.
  - Tracked `MachineLearningRating_v3.txt` with DVC for versioning.

## Key Insights from EDA

- **Loss Ratio**: Varies by Province, with some regions showing higher risk.
- **Outliers**: Extreme TotalClaims values suggest potential fraud or high-risk policies.
- **Temporal Trends**: Claim frequency shows patterns (seasonal or sporadic, pending date column verification).
- **Vehicle Makes**: Certain makes have higher Loss Ratios, indicating riskier profiles.
- **Visualizations**:
  - Heatmap of claim frequency by Province and VehicleType.
  - Pair plot of numerical variables (e.g., TotalPremium, TotalClaims).
  - Stacked bar chart of claim severity by Gender and CoverType.
  - Time-series plot of claim frequency (assumes `VehicleIntroDate`).

## Notes

- **Dataset**: Assumes `MachineLearningRating_v3.txt` contains columns like `TotalPremium`, `TotalClaims`, `Province`, `VehicleType`, etc. Adjust column names in `eda.ipynb` if they differ.
- **Temporal Analysis**: The time-series plot uses `VehicleIntroDate`. If no date column exists, update or skip this visualization.
- **DVC Storage**: Replace `/path/to/local/storage` with a valid path (e.g., `C:\Users\Gedion Afework\dvc_storage`).

## References

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Documentation](https://seaborn.pydata.org/)
- [DVC Documentation](https://dvc.org/doc)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

## License

MIT License
