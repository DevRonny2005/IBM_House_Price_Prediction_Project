# House Price Prediction Dashboard

A Streamlit web app that predicts a house price from its area, number of bedrooms, bathrooms, and parking spaces. The app trains a Linear Regression model from the included dataset and presents an interactive dashboard with charts.

## Features

- Predict a house price from user-entered house details
- Display the estimate in Indian Rupees (INR)
- Compare the estimate with the dataset average
- Show model quality metrics: R² score and Mean Absolute Error
- Explore actual-versus-predicted prices, average price by bedrooms, price distribution, and feature impact
- Preview the dataset and its statistical summary

## Project files

```text
HOME_PREDICT_PROJECT/
|-- app.py
|-- HOUSE_PRICE_PREDICTION.csv
|-- requirements.txt
`-- README.md
```

## Requirements

- Python 3.9 or later
- The packages listed in `requirements.txt`

Your `requirements.txt` should contain:

```text
streamlit
pandas
scikit-learn
```

## Installation

Open PowerShell in the project folder and run:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

If PowerShell prevents activation, use this temporary setting first:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

Alternatively, install and run without activating the environment:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m streamlit run app.py
```

## Run the application

With the virtual environment active, run:

```powershell
python -m streamlit run app.py
```

Streamlit will display a local URL, usually `http://localhost:8501`. Open it in your browser.

## Dataset format

The application expects `HOUSE_PRICE_PREDICTION.csv` to be in the same folder as `app.py`, with these columns:

| Column | Description |
| --- | --- |
| `price` | House price (target value) |
| `area` | House area in square feet |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `parking` | Number of parking spaces |

## How it works

1. The app loads the CSV dataset.
2. It uses `area`, `bedrooms`, `bathrooms`, and `parking` as input features.
3. It trains a Linear Regression model using 80% of the dataset.
4. It tests the model on the remaining 20% and displays its performance.
5. When you enter house details, the trained model predicts an estimated price.

## Troubleshooting

**`streamlit` is not recognized**

Install dependencies, then run the app through Python:

```powershell
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

**CSV file not found**

Ensure `HOUSE_PRICE_PREDICTION.csv` is in the same folder as `app.py`, and check that the filename exactly matches the name used in the code.

**The browser page is blank**

Save `app.py`, review the PowerShell terminal for an error message, stop the app with `Ctrl + C`, then run it again.
