# Monte Carlo Simulation for Gold Price in INR

This project performs a comprehensive data science analysis and Monte Carlo simulation to forecast the price of gold in Indian Rupees (INR). It fetches historical data, calculates key statistical metrics, runs a Geometric Brownian Motion (GBM) simulation, and provides detailed analysis and visualizations.

## Project Structure

The project is organized into a modular structure for clarity and maintainability:

```
monte_carlo_gold/
├── data_fetcher.py          # Functions to fetch gold price data from Yahoo Finance
├── data_processor.py        # Data cleaning, preprocessing, and metric calculation
├── monte_carlo_simulator.py # Core Monte Carlo simulation implementation (GBM)
├── analyzer.py              # Statistical analysis of simulation results
├── visualizer.py            # All plotting and visualization functions
├── main.py                  # Main execution script to run the entire project
├── requirements.txt         # All Python dependencies for the project
├── output/                  # Directory for all generated outputs
│   ├── visualizations/      # All generated charts and plots (PNGs)
│   ├── simulation_results.csv # Raw data from all simulation paths
│   └── executive_summary.txt  # High-level report of findings
└── README.md                # This documentation file
```

## Methodology

The simulation is based on the **Geometric Brownian Motion (GBM)** model, a widely used stochastic model for financial time series. The formula is:

*S_t = S_0 * exp((μ - 0.5σ²)t + σW_t)*

Where:
- `S_t` = Price at time `t`
- `S_0` = Starting price (latest known price)
- `μ` = Drift (long-term trend of returns)
- `σ` = Volatility (standard deviation of returns)
- `W_t` = Wiener process (a random walk component)

The historical daily returns are calculated using logarithmic returns: `log(P_t / P_{t-1})`.

## How to Run the Project

### 1. Setup the Environment

First, clone the repository and navigate into the project directory. It is highly recommended to use a virtual environment to manage dependencies.

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
```

### 2. Install Dependencies

Install all the required libraries using the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

### 3. Run the Simulation

Execute the `main.py` script to run the entire pipeline from data fetching to report generation.

```bash
python main.py
```

The script will print a summary of its progress and the final executive summary to the console.

## Output Deliverables

After running `main.py`, the following outputs will be generated in the `output/` directory:

1.  **Executive Summary Report (`executive_summary.txt`)**: A text file containing a high-level summary of the historical analysis, simulation predictions, risk assessment, and investment insights.
2.  **High-Quality Visualizations (`output/visualizations/`)**: A folder containing several PNG plots, including:
    - Historical price trends
    - Distribution of daily returns
    - Monte Carlo simulation paths
    - Distribution of final prices
    - A fan chart showing confidence intervals
3.  **Simulation Data (`simulation_results.csv`)**: A CSV file containing the raw price data for every simulated path over the forecast period. This can be used for further, more detailed analysis.

## Required Libraries

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scipy`
- `yfinance`
- `datetime`
