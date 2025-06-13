# ACIS Car Insurance Analytics

## Overview

This repository contains the data analytics pipeline for AlphaCare Insurance Solutions (ACIS) to optimize car insurance marketing strategies in South Africa. The project focuses on analyzing historical insurance claim data to identify low-risk targets and reduce premiums for attracting new clients.

## Objectives

- Perform Exploratory Data Analysis (EDA) to uncover patterns in risk and profitability.
- Develop a reproducible data pipeline using Data Version Control (DVC).
- Optimize marketing strategies by identifying low-risk customer segments.

## Repository Structure

- `data/`: Datasets (tracked by DVC).
- `notebooks/`: Jupyter notebooks for EDA.
- `scripts/`: Python scripts for data processing.
- `requirements.txt`: Project dependencies.
- `.github/workflows/`: CI/CD configuration.

## Setup Instructions

1. Clone the repository: `git clone https://github.com/GedionAfework/AlphaCare-Insurance-Solutions.git`
2. Create a virtual environment: `python -m venv .venv`
3. Activate the environment: `source .venv/bin/activate` (Linux/macOS) or `.venv\Scripts\activate` (Windows)
4. Install dependencies: `pip install -r requirements.txt`
5. Initialize DVC: `dvc init`

## License

MIT License
