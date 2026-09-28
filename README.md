# Supply Chain Optimization System

A Streamlit dashboard for exploring supply-chain data and producing cost, inventory, demand, supplier, optimization, and recommendation insights.

## Features

- Upload and inspect CSV supply-chain datasets.
- Analyze costs from supported price, purchase, holding, and transportation columns.
- Identify inventory and demand-coverage conditions for human review.
- Produce review-oriented recommendations; the system does not automate procurement actions.
- Export displayed data as CSV and, when available, Excel.
- Includes modular analysis code and automated tests.

## Technology Stack

- Python
- Streamlit
- Pandas and NumPy
- OpenPyXL for Excel export
- Pytest for testing

## Project Structure

```text
Supply-Chain-Optimization/
├── app.py                 # Streamlit entry point
├── data/
│   └── sample_data.csv    # Example input dataset
├── modules/               # Analysis and recommendation logic
├── tests/                 # Automated tests
├── utils/                 # Validation and export helpers
├── requirements.txt
└── pytest.ini
```

## Required Dataset Columns

The sample file in `data/sample_data.csv` is a valid starting point. For the current dashboard, use a CSV with these columns where applicable:

| Area | Supported columns |
| --- | --- |
| Item identifier | `Item`, `Item Name`, `Product`, `Product Name`, `SKU`, or `Item ID` |
| Inventory | `Current Stock`, `Reorder Point`, `Max Stock Level` |
| Cost | `Unit Price`, `Purchase Cost`, `Holding Cost`, `Transportation Cost` |
| Category | `Category`, `Item Category`, `Product Category` |

## Run Locally on Windows

Use Python 3.10 or later. A fresh virtual environment is recommended.

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
streamlit run app.py
```

Then open the local address shown by Streamlit and upload `data/sample_data.csv`.

## Run Tests

```powershell
python -m pytest tests/ -v
```

## Current Integration Note

The project contains modules for inventory, demand, demand prediction, and supplier analysis. Their Streamlit pages are currently placeholders and must be connected to their respective module functions before those four dashboard pages can display results. Cost analysis, optimization, recommendations, reporting, data upload, and exports are already wired into `app.py`.

