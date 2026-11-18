# Agriculture Raw Material Analysis

An exploratory analysis of monthly prices for 12 agricultural raw materials from 1990 to 2020. I looked at which commodities grew the most, which were the riskiest and whether their prices move together.

## Dataset

`agricultural_raw_material.csv` from Kaggle, with 361 monthly rows (April 1990 to April 2020) covering coarse wool, fine wool, copra, cotton, hard log, hard sawnwood, hide, plywood, rubber, softlog, soft sawnwood and wood pulp.

## Tools

Python, pandas, matplotlib, seaborn

## Data Cleaning

* Standardised column names and converted dates and prices to the right types
* Dropped the original % change columns, since returns are calculated from prices
* Checked for exact duplicates, missing months and zero or negative prices (none found)
* Left missing values empty, since they come from series that end early (June 2017 for most, June 2018 for copra) and filling them would mean making up data
* Noted that wood pulp stays at 875 for its last 72 months, which looks like a repeated value in the source

## Analysis

* Price trends and total growth
* Monthly returns and volatility
* Descriptive statistics and coefficient of variation
* Highest and lowest prices
* Correlation of prices and of monthly returns
* 12 month moving average

## Key Findings

* Copra grew the most (about 164%), followed by coarse wool (about 121%). Hide and cotton were the only ones to fall.
* Soft sawnwood, copra and rubber were the most volatile. Plywood and hard sawnwood were the most stable.
* Six commodities peaked in 2011 or 2012.
* Prices look strongly correlated, but month to month only coarse and fine wool, and hard log and plywood, really move together.

## Limitations

* Prices are in different units, so growth, returns and CV are better for comparing commodities than raw prices.
* Several series end in 2017 or 2018, so they cover a shorter period.

## How to Run

```
pip install pandas matplotlib seaborn jupyter
```

Change the path in `pd.read_csv()` to point to `agricultural_raw_material.csv`, then run all cells.

## Files

* `eda1-agriculture-raw-material.ipynb`: the notebook
* `agricultural_raw_material.csv`: the dataset
