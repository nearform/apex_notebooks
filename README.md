# Apex Notebooks: Data Consolidation and Exploration

This project contains Jupyter notebooks and supporting files for consolidating, exploring, and validating investment-related data for the Apex Group. The main notebook, `01_Data_Consolidation_and_Exploration.ipynb`, demonstrates how to load, inspect, and validate data from multiple Excel files covering investors, accounts, managed funds, transactions, and fund operations.

## Project Structure

- `01_Data_Consolidation_and_Exploration.ipynb` — Main notebook for data loading, exploration, and validation.
- `data_files/` — Contains all required Excel data files (not tracked in version control).
- `docs/` — Documentation and project notes.

## Getting Started

1. Clone this repository.
2. Place all required Excel files in the `data_files/` directory (see below). Source file are on gDrive: Sales/Clients/Apex ...
3. Open the notebook in VS Code or Jupyter and run the cells.

### Required Data Files
- Investors.xlsx
- Investors Account.xlsx
- Managed Funds.xlsx
- Transactions With Details.xlsx
- Fund Ops Transactions 2010-2018.xlsx
- Fund Ops Transactions 2019-2020.xlsx
- Fund Ops Transactions 2021.xlsx
- Fund Ops Transactions 2022.xlsx
- Fund Ops Transactions 2023.xlsx
- Fund Ops Transactions 2024.xlsx
- Fund Ops Transactions 2025.xlsx

> **Note:** The `data_files/` directory is excluded from version control for privacy and size reasons. You must provide these files locally.

## Features
- Loads and consolidates multiple Excel files into pandas DataFrames.
- Performs schema inspection and data validation checks.
- Assesses relationships and referential integrity between datasets.

## Requirements
- Python 3.8+
- pandas
- Jupyter or VS Code with Jupyter extension

## Usage
Open the main notebook and execute each cell in order. Review outputs for data quality and integrity issues.

## License
Proprietary. For internal use by Apex Group only.
