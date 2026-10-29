# Infosys Stock Volatility Analysis using TARCH Model

This project analyzes the 10-year historical stock price volatility of Infosys (INFY.NS) using financial time-series modeling. It fetches historical data, calculates daily returns, and fits a Threshold ARCH (TARCH / GJR-GARCH) model to estimate and visualize conditional volatility[cite: 1].

## Prerequisites
To run the code, you need the following Python libraries installed[cite: 1]:
* `pandas`
* `yfinance`
* `arch`
* `matplotlib`
* `seaborn`

## Methodology
1. **Data Collection:** Downloads 10 years of historical close prices for Infosys (`INFY.NS`) using the `yfinance` API[cite: 1].
2. **Return Calculation:** Computes the daily percentage change (returns) of the stock price, filling missing values with 0[cite: 1].
3. **Model Fitting:** Configures and fits a GJR-GARCH (TARCH) model (`p=1, o=1, q=1`, `vol='GARCH'`) to the return data using the `arch` library[cite: 1].
4. **Visualization:** Compares the calculated absolute real volatility against the TARCH conditional volatility using a custom `seaborn` line plot[cite: 1].

## Outcome and Results

### Model Summary
The TARCH (GJR-GARCH) model yielded the following statistical outcomes based on 2,471 observations[cite: 1]:
* **Log-Likelihood:** -4704.73[cite: 1]
* **AIC:** 9419.46[cite: 1]
* **BIC:** 9448.52[cite: 1]

**Mean Model (Constant Mean):**
* **mu:** 0.0835 (p-value: 0.007)[cite: 1]

**Volatility Model:**
* **omega:** 0.3036[cite: 1]
* **alpha[1]:** 0.0638[cite: 1]
* **gamma[1]:** 0.0746[cite: 1]
* **beta[1]:** 0.7956 (p-value: < 0.001)[cite: 1]

### Visualization
The script successfully generates a line chart titled **"TARCH-Model for Infosys 10years Stock Price Volatility"**[cite: 1]. 
* **Navy Line:** Represents the Real Volatility (absolute daily returns)[cite: 1].
* **Red Line:** Represents the TARCH Conditional Volatility predicted by the model[cite: 1]. 
* The plot is formatted without right and top spines for a cleaner visual representation of the financial data over time[cite: 1].
