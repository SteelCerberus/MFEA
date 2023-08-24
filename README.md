# MFEA

MFEA stands for Modern_Football's Excellent Adventure, which can alternatively be shortened to MF'rs Excellent Adventure.

The strategy combines volatility clustering, momentum, and leverage to generate outsized returns with risk lower than that of 2x leverage.

This repository contains a Python script and a Jupyter Notebook to backtest MFEA in an easily customizable way.

# Getting Started

## Jupyter Notebook

This is recommended over the Python script due to ease of use.

1. If not already done, install Jupyter Lab or Jupyter Notebook. It is highly recommended to get an extension to collapse cells.
2. Create a virtual environment for the project.
3. Through your preferred method, download and open MF'rs Excellent Adventure.ipynb and daily_us_market_data.csv
4. Install all required libraries.
5. In the cell containing the line EXTENDED_DATA_PATH = r'data/daily_us_market_data.csv', change the path to where you have stored daily_us_market_data.csv. This can be an absolute or relative path.
6. Run all cells in order.

## Python Script

1. Create a virtual environment for the project.
2. Through your preferred method, download and open MF'rs Excellent Adventure.ipynb and daily_us_market_data.csv
3. Install all required libraries.
4. In the line EXTENDED_DATA_PATH = r'data/daily_us_market_data.csv', change the path to where you have stored daily_us_market_data.csv. This can be an absolute or relative path.
5. Run the script. Windows will open containing plots. Once done looking at these, close the plot to have the script continue running.

# Data sources 

Part of the repository is a file containing daily U.S. risk free rate and stock market data from April 1, 1885 to June 1, 2023. The following lists the sources.

## Close Data Sources:

Note: A 0.0945% expense ratio is applied throughout. (SPY expense ratio as of June 1, 2023)

**From April 1, 1885 to January 3, 1928:**

Dow Jones composite index data

https://www.billschwert.com/dstock.htm

**From January 4, 1928 to July 2, 1962:**

S&P composite index data

https://www.billschwert.com/dstock.htm

**From July 3, 1962 to January 28, 1993:**

^GSPC with monthly dividends added

https://finance.yahoo.com/quote/%5EGSPC

https://discord.com/channels/879215803520663652/1027725522739925012/1087903098405666886

**From January 29, 1993 to June 1, 2023:**

SPY data from Yahoo Finance

https://finance.yahoo.com/quote/SPY

## Risk Free Rate Data Sources:

**From April 1, 1885 to December 29, 1933:**

10-year treasury note data, interpolated to daily, 1% subtracted

http://www.econ.yale.edu/~shiller/data.htm

**From January 1, 1934 to June 1, 2023:**

3-month treasury bill data, interpolated to daily

https://fred.stlouisfed.org/series/TB3MS
