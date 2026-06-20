# Value at Risk (VaR) Portfolio Analysis

## Overview

This project implements a complete **market risk analysis framework** for an equity portfolio using Python.

The application estimates the **Value at Risk (VaR)** and **Expected Shortfall (CVaR)** of a portfolio through three complementary methodologies:

* Historical Simulation
* Parametric (Variance-Covariance) Method
* Monte Carlo Simulation

The project also includes:

* Portfolio return calculation
* Risk statistics (volatility, skewness, kurtosis)
* VaR backtesting
* Monte Carlo scenario generation
* Automated dashboard visualization

---

## Features

### Portfolio Analytics

* Multi-asset portfolio support
* Custom portfolio weights
* Daily portfolio return calculation
* Descriptive statistics

### Risk Metrics

#### Historical VaR

Estimates risk directly from historical returns without distributional assumptions.

#### Parametric VaR

Assumes returns follow a normal distribution and computes VaR analytically.

#### Monte Carlo VaR

Generates thousands of simulated portfolio returns to estimate tail risk.

#### Expected Shortfall (CVaR)

Measures the average loss beyond the VaR threshold.

### Backtesting

Compares realized losses against predicted VaR levels and reports:

* Number of exceptions
* Expected exceptions
* Exception rate

### Visualization Dashboard

The program generates a dashboard containing:

1. Distribution of historical returns and VaR thresholds
2. Backtesting results
3. Monte Carlo loss distribution
4. Comparison of VaR methodologies

---

## Example Output

### Portfolio Configuration

| Asset | Weight |
| ----- | -----: |
| AAPL  |    30% |
| MSFT  |    25% |
| JPM   |    25% |
| XOM   |    20% |

Portfolio Value: **€100,000**

Confidence Level: **99%**

Investment Horizon: **1 Day**

### Example Results

| Method      | VaR (%) | VaR (€) |
| ----------- | ------: | ------: |
| Historical  |  -1.34% | 1,342 € |
| Parametric  |  -1.45% | 1,452 € |
| Monte Carlo |  -1.45% | 1,448 € |

Expected Shortfall:

| Method     |  ES (€) |
| ---------- | ------: |
| Historical | 1,484 € |
| Parametric | 1,673 € |

---

## Project Structure

```text
var-portfolio/
│
├── main.py
├── README.md
├── requirements.txt
├── var_portfolio_resultats.png
│
├── data/
├── notebooks/
└── src/
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/joshuacoureau12/var-portfolio.git
cd var-portfolio
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it:

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Required Packages

```text
numpy
pandas
matplotlib
scipy
yfinance
```

Generate the requirements file:

```bash
pip freeze > requirements.txt
```

---

## Usage

Run the application:

```bash
python main.py
```

The program will:

1. Download market data using Yahoo Finance
2. Compute portfolio returns
3. Calculate VaR and Expected Shortfall
4. Perform backtesting
5. Generate visual reports

Output file:

```text
var_portfolio_resultats.png
```

---

## Methodology

### Historical VaR

The VaR is computed as the empirical quantile of historical portfolio returns:

[
VaR_\alpha = Q_\alpha(R)
]

### Parametric VaR

Assuming normally distributed returns:

[
VaR = \mu + z_\alpha \sigma
]

where:

* μ = mean return
* σ = volatility
* zα = confidence quantile

### Monte Carlo VaR

Simulated returns are generated using:

[
R_t = \mu + \sigma Z
]

with:

[
Z \sim N(0,1)
]

The VaR corresponds to the selected tail percentile of simulated returns.

---

## Future Improvements

* Conditional VaR (CVaR) optimization
* Multi-day VaR estimation
* GARCH volatility models
* Stress testing scenarios
* Interactive dashboard with Plotly
* Portfolio optimization
* Risk attribution by asset

---
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/joshuacoureau12-creator/var_portfolio/blob/main/var-portfolio.ipynb)
---

## Disclaimer

This project is intended for educational and research purposes only.

The calculations presented do not constitute financial advice and should not be used as the sole basis for investment decisions.

---

## Author

Developed as a quantitative finance and risk management project using Python.

Feel free to fork, improve, and contribute.
