# TimeSeries_Decomposition_ARIMA_Model

### Machine Learning (ML) gets a lot of hype, but its classical predecessors are still immensely powerful, especially in the time-series space. Error, Trend, Seasonality Forecast (ETS), Autoregressive Integrated Moving Average (ARIMA) and Holt-Winters are three Classical methods that are not only incredibly popular but are also excellent time-series predictors.

## Decompose Time Series Data

A useful abstraction for selecting forecasting methods is to break a time series down into systematic and unsystematic components.
•	Systematic: Components of the time series that have consistency or recurrence and can be described and modeled.
•	Non-Systematic: Components of the time series that cannot be directly modeled.
A given time series is thought to consist of three systematic components including level, trend, seasonality, and one non-systematic component called noise.
These components are defined as follows:
•	Level: The average value in the series.
•	Trend: The increasing or decreasing value in the series.
•	Seasonality: The repeating short-term cycle in the series.
•	Noise: The random variation in the series.

Obviously, we want the residuals to be as small as possible.
we compare additive and multiplicative residuals, we can see that the later is much smaller (multiplicative residual). As a result, a multiplicative model (Trend x Seasonality) fits the original data much more closely.

## Holt winters & Exponential smoothing
Holt-Winters is a model of time series behavior. Forecasting always requires a model, and Holt-Winters is a way to model three aspects of the time series: a typical value (average), a slope (trend) over time, and a cyclical repeating pattern (seasonality).
The Holt-Winters forecasting method applies a triple exponential smoothing for level, trend and seasonal components.
Single Exponential Smoothing (SES) agrees with the Naïve method in that future values can be predicted from the looking at the past, but it goes a bit further to say that what has happened most recently will have the largest impact on what will happen next. A forecast from SES is just an exponential weighted average.

Exponential smoothing retains all older periods while giving a greater weight to more recent periods (hence not a MOVING average).
Box–Jenkins Methodology
•Model identification and model selection
–Make sure variables are stationary.  Difference as necessary to get a constant mean and transformations to get constant variance.
–Check for seasonality: Decays and spikes at regular intervals in ACF plots.
•Parameter estimation
–Compute coefficients that best fit the selected model.
•Model checking
–Check if residuals are independent of each other and constant in mean and variance over time (white noise).


## AutoRegressiveIntegrated Moving Average -ARIMA(p,d,q) Model

•p is the number of autoregressive [AR(p)] terms (a linear regression of the current value of the series against one or more prior values of the series)
•d is the number of non-seasonal differences (order of the differencing) used to make the time series stationary [I(d)]
•q is the order of the moving average [MA(q)] model
–Maximum lag beyond which the ACF is 0 when ACF shows a sharp cutoffand/or lag1 autocorrelation is negative, i.e., the series is slightly overdifferenced.

White Noise is a random signal with equal intensities at every frequency and is often defined in statistics as a signal whose samples are a sequence of unrelated, random variables with no mean and limited variance. In some cases, it may be required that the samples are independent and have identical probabilities.

If residuals are white noise (purely random)…

A sign that model predictions are not white noise is an indication that further improvements to the forecast model may be possible.
•Non-seasonal ARIMA models are denoted ARIMA(p,d,q)
•Seasonal ARIMA (SARIMA) models are denoted ARIMA(p,d,q)(P,D,Q)m, where m refers to the number of periods in each season and (P,D,Q) refer to the autoregressive, differencing and moving average terms of the seasonal part of the ARIMA model.

Time series decomposition generally involves partitioning a signal into seasonal, trend, residual and sometimes level, holiday etc. components, which assumes additive or multiplicative relationships.
In ARIMA, there isn't a decomposition of such type. It's a generalization of ARMA models, in which we first difference the series and fit an ARMA model.

## Times Series Forecasting on US carrier Revenue Passenger Data.

### Time Series Forecasting Model Evaluation -MAPE

Forecast window (months)	Holt-Winters	Manual ARIMA1	Manual ARIMA2	Auto ARIMA 
3	1.18%	0.65%	0.41%	0.45%
6	1.81%	1.20%	0.74%	0.85%
12	1.88%	1.62%	1.20%	1.12%
18	2.10%	1.92%	1.28%	1.14%
24	2.03%	2.28%	1.24%	1.11%
36	1.98%	3.58%	1.62%	1.61%

MAPE should be lesser for better model performance.



