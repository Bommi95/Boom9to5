# ETF Portfolio Optimization

Given the uncertainty about the future performance of ﬁnancial markets, investors typically diversify their portfolios to improve the quality of their returns. In this project, I constructed a portfolio composed of two ETFs (exchange traded funds) that tracks US equity and ﬁxed income markets. The equity ETF tracks the widely followed S&P 500 while the ﬁxed income ETF tracks long-term US Treasury bonds. I used optimization techniques to determine what fraction of money should be allotted to each asset (i.e., portfolio weights) by forming an optimal portfolio using the Sharpe ratio with historical data (from 2003 to 2013) and examine its performance over a test period(2014). 

The data for the two assets were downloaded from Google Finance (ticker symbols: SPY, TLT) and the federal funds interest rate, representing the risk free rate, was taken from the U.S. Federal Reserve Bank website.

The data are splited into training and testing subsets.  The training data is used to compute the portfolio weights and testing set is used to evaluate our portfolio. I computed the rate of return for the S&P 500 and long term treasury bonds ETF asset, and constructed a time series of data with the returns for both assets plotted.
   <p align="center">
  <img width="460" height="300" src="https://github.com/Bommi95/ETF-Portfolio-Optimization/blob/master/total%20returns.png">
</p>  
I computed the rolling window correlation with a window of 24 weeks of data (i.e., weeks 1 to 24, weeks 2 to 25...) and constructed a time series plot of the rolling window correlation with each point plotted on the last day of the window.
   <p align="center">
  <img width="460" height="300" src="https://github.com/Bommi95/ETF-Portfolio-Optimization/blob/master/rolling%20window%20cor.png">
</p>  

I computed sharpe ratio for each assets on training set and create a function which takes a vector of portfolio weight and a vector of the return of both assets as input, using equation below to obtain the returns for the portfolio. 
   <p align="center">
  <img width="406" height="51" src="https://github.com/Bommi95/ETF-Portfolio-Optimization/blob/master/return%20formula.PNG">
</p> 
For each weight value in my vector x, the function compute the Sharpe ratio for the corresponding portfolio. I used STAT_FUNCTION() to plot the result to see which portfolio weight produces the maximum Sharpe ratio. 
   <p align="center">
  <img width="460" height="300" src="https://github.com/Bommi95/ETF-Portfolio-Optimization/blob/master/sharpe_ratio_optim.png">
</p> 

It can be seen that the portfolio returns reach its maximum when weights allocation for S&P 500 around 0.6 (x=0.6).
