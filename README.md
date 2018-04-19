# Model Based Trading

## Group 1 Project

__This project is to create an adaptive VWAP trading strategy with optimal execution.__

Members: Wenting Ge, Lenny Jin, Yuanyi Liang, Jiaying Lu, Johnson Wu, Yilun Yao

<br>

## Strategy workflow

1. Read and process data
	* Pre-process and generate Min bar Data
	* Pre-process and generate Tick Data
	* Filter Tick Data to remove data with an abnormal price change
2. Get the static trading curve using 2 methods
	* Method 1: by regression
	* Method 2: by binwise median
3. Trading signals functions
	* VCV measure
		* logistic regression
	* VPIN measure
		* threshold
	* Hidden Liquidity
		* optimization
4. Calibrate delta parameter in generating adaptive trading curve
	* Grid search
5. Generate dynamic trading curve
	* Update dynamic trading curve based on signals
6. Backtest on Min bar data
	* Generate trades for result analysis
7. Train and calibrate parameters in execution model
	* Exponential fit
8. Test on tick data
	* Compare VWAP and order completion price
10. Transaction cost analysis
	* Compare VWAP, order completion price and other measures
	* Compare performance of different signals
11. Visualization
	* Scatter plot
	* Box chart
	* Bubble chart
  
<br>

## Usage

Please download the following notebooks and data files and put the data files in the path */Data/*

1. [mbt_g1_strategy](https://github.com/wuyouk/Model-Based-Trading/blob/master/adaptive_vwap_main.ipynb)
2. [mbt_g1_signal_liquidity](https://github.com/wuyouk/Model-Based-Trading/blob/master/Hidden%20Liquidity/HiddenLiquidity_v1.0_APPL.ipynb)
3. [tick data AAPL_20180117](https://github.com/wuyouk/Model-Based-Trading/blob/master/Data/tick_AAPL_20180117.gz)
4. [bar data AAPL_170101_180413](https://github.com/wuyouk/Model-Based-Trading/blob/master/Data/bar_AAPL_170101_180413.csv)
5. [liquidity_training_data](https://github.com/wuyouk/Model-Based-Trading/tree/master/Hidden%20Liquidity/Data)

Note: For part of the visualization, you need to have a plotly account and set credentials in the first block ```tls.set_credentials_file(username=' ', api_key=' ')```

<br>

## Data source

1. [Dukascopy](http://www.dukascopy.com)
2. [NxCore](http://nxcoreapi.com/doc/)
3. [TickData](https://www.tickdata.com/equity-data/)
4. [Finam](http://www.finam.ru)
5. [Google Finance](https://www.google.com/finance/getprices?i=[PERIOD]&amp;p=[DAYS]d&amp;f=d,o,h,l,c,v&amp;df=cpct&amp;q=[TICKER])
