# MFEA

MFEA stands for Modern_Football's Excellent Adventure, which can alternatively be shortened to MF'rs Excellent Adventure.

The strategy combines volatility clustering, momentum, and leverage to generate outsized returns with risk lower than that of 2x leverage.

This repository contains a Jupyter Notebook to backtest MFEA in an easily customizable way.

# Getting Started

1. If not already done, install Jupyter Lab or Jupyter Notebook. It is highly recommended to get an extension to collapse cells. Here is a tutorial: https://towardsdatascience.com/how-to-set-up-anaconda-and-jupyter-notebook-the-right-way-de3b7623ea4a
   
2. In a command line interface, run git clone https://github.com/SteelCerberus/MFEA.git

3. Create a virtual environment for the project.
   
4. Install all required libraries.
   
5. Open mfea.ipynb and run all cells.

Want a custom font? For some reason, this is a very complicated process. Here are the steps that worked for me on Windows 10 using Anaconda on Jupyter Notebook:

1. Download custom font from Google Fonts or some other site in the .ttf format

2. Copy the indvidual .ttf file to C:\\Users\\{username}\\anaconda3\\envs\\{env name}\\Lib\\site-packages\\matplotlib\\mpl-data\\fonts\\ttf

3. Go to C:\\Users\\{username}\\.matplotlib and delete the fontlist.json file
  
4. Relaunch notebook and run some lines of code

5. New fontlist file should appear, and font should be working

# FAQ

**Q: What is the METHOD parameter for?**

A: The method determines how allocations are chosen from signals. Look at the state_to_allocation_dict method in the Backtest class to see the possible methods and what they allocate.

**Q: What is the USE_MODIFIED_SP_500 parameter for?**

A: A formula courtesy of modern_football himself allows you to manipulate close data to have a specific CAGR and volatility. Setting USE_MODIFIED_SP_500 to True will apply this formula using the values supplied in MODIFIED_SP_500_CAGR and MODIFIED_SP_500_VOL.

**Q: Why is the modified CAGR off?**

A: This happens because the CAGR given is applied over the ENTIRE time period of S&P 500 data available. However, when the backtest is done, a chunk of the start is cut off because momentum needs to be calculated before making an initial allocation. Volatility will also be a bit off because of this, but it isn't as noticeable because volatility is mean reverting.

**Q: There's too much here. Tell me what to invest in.**

A: Set USE_EXTENDED_DATA to False. Set USE_DAILY_TBILL to True. Set SP_500_TICKER to 'SPY', 'VFINX', 'VFIAX', or any other S&P 500 fund. Run the script. One of the printed out lines after all the charts will state the current allocation.
    
# Data sources 

Under the data directory is KMLM data (January 1, 1992 to November 30, 2020) and U.S. risk free rate & stock market data (April 1, 1885 to June 1, 2023).

KMLM data was aquired by hydromod through emailing KFA Funds. The U.S. market data was sourced from the following:

## Stock Close Data Sources:

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

(Do not take this as financial advice. Use at your own risk.)
