Stock Market Dashboard 📈
An interactive Tableau dashboard that visualizes historical stock data for six major tech companies: Apple, Facebook (Meta), Google, Nvidia, Tesla, and Twitter. The dashboard is powered by preprocessed data generated with Python (Pandas) and includes key technical indicators like moving averages, daily price changes, and volume trends.

🔍 Overview
This project demonstrates an end-to‑end data pipeline:
Data Acquisition – Raw daily stock price CSV files (from Yahoo Finance or similar).
Data Preprocessing – A Jupyter notebook (stocksdashboard.ipynb) that reads the CSVs, calculates moving averages (50‑day and 200‑day), lagged columns, and day‑over‑day changes, then exports clean, feature‑enriched CSV files.
Dashboard Creation – The enriched data is loaded into Tableau to build an interactive dashboard that allows users to explore stock performance over time, compare companies, and analyze volatility.

📁 Data Sources
The raw data consists of six CSV files (one per company) located in the archive/stocks/ folder. Each file contains daily trading data with the following columns:
Date, Open, High, Low, Close, Adj Close, Volume

The files cover different time spans (e.g., Apple from 1980, Facebook from 2012, etc.) and were originally downloaded from sources like Yahoo Finance.

🛠️ Data Preprocessing (Python + Pandas)
The Jupyter notebook stocksdashboard.ipynb performs the following steps for each stock:

Load Data – Reads the CSV into a pandas DataFrame.
Moving Averages – Adds MA50 and MA200 columns (rolling mean of Close over 50 and 200 days).
Lagged Columns – Creates Previous Day close price using shift(1).
Price Changes – Computes Change in price (Close – previous close) and Percent change in price (daily return).
Volume Analysis – Adds Previous day volume, Change in volume, and Percent change in volume.
Export – Saves the enriched DataFrame as a new CSV: Apple.csv, Facebook.csv, Google.csv, Nvidia.csv, Tesla.csv, Twitter.csv.
All calculations are done in a loop, making it easy to extend to more stocks.

📊 Tableau Dashboard Features
The Tableau workbook (not included here, but described from the provided image) brings the data to life with multiple interactive views.

🧩 Header Section
Start / End Date filters (default: 2020‑04‑01)

Company filter (select one or multiple)
Last Day summary cards:
Total volume in the period
Lowest price in the period
Highest price in the period

📈 Volume Chart (Area Chart)
Shows trading volume over time (2015–2020) for the selected companies.
X‑axis: Date (month‑year ticks like "1 Nov 15", "1 May 16", …)
Y‑axis: Volume in millions.

📋 Detailed Price Table
A tabular view showing each company’s latest closing price, the previous day’s close, the absolute change in price, and the percentage change. Green up‑arrows (▲) indicate positive changes, red down‑arrows (▼) indicate negative changes. This gives a quick snapshot of daily performance for all selected stocks.

📋 Detailed Volume Table
Similarly, a table displays the most recent trading volume alongside the previous day’s volume and the absolute change in volume. This helps identify unusual trading activity or volume spikes.

📊 Price Percent Change Bar Chart
Horizontal bars representing the daily percent change for each company. Positive changes extend to the right, negative to the left, enabling an at‑a‑glance comparison of relative daily moves.

📉 Moving Average – Open Price Line Chart
Overlays the 50‑day moving average (MA50) and 200‑day moving average (MA200) on the same axis as the daily open price, for selected companies. This classic technical analysis view helps spot trends and potential buy/sell signals (e.g., golden cross / death cross).

🏷️ Measure Names Legend
Interactive legend to toggle between MA200, MA50, and Open price on the moving average chart. Users can focus on the lines they care about.


💡 Tip: If you want to skip the preprocessing, the exported CSV files are also included in the repository.

🧰 Requirements
Python 3.7+ with pandas
Jupyter Notebook or JupyterLab
Tableau Desktop (Public Edition is free and sufficient)

🙌 Acknowledgements
Data originally sourced from Yahoo Finance.

Inspired by the need for a simple yet powerful stock analysis tool.

