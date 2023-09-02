Autocorrelation: correlation between current and lagged values.

Autocorrelation function (ACF): correlation coefficients (y-axis) vs lag values(x-axis)
Autocorrelation is always 1 at lag 0.
When there is a trend, the autocorrelation is high for small lags and it gradually decreases as the lag increases.

Partial Autocorrelation function (PACF): correlation between present value and residuals of previous lag. 
If ACF is a decaying sinusoidal, it indicates presence of autoregressiveness. Plotting PACF helps find the order of the AR model. 

ARMA (Auto-Regressive Moving Averages):

AR:
	AR(p) model; p->order
$$ x_{t}= c + ϕ_1 x_{t-1} + ... + ϕ_p x_{t-p} + ϵ_t$$
MA:
	MA(q) model; q->order
$$ x_{t}= ϵ_t + θ_1ϵ_{t-1} + ... + θ_qϵ_{t-q}$$ ARMA:

$$ x_{t}= ϕ_1 x_{t-1} + ... + ϕ_p x_{t-p} + ϵ_t + θ_1ϵ_{t-1} + ... + θ_qϵ_{t-q}$$
 
Dickey Fuller test for checking if data is stationary
If not:
De-trend and de-seasonalize to make it stationary by:
- transformation (e.g.: log, square root, etc.)
- smoothing (e.g.: weekly average, monthly average, rolling average)
- differencing (e.g.: first order differencing)
- polynomial fitting
- decomposition

Now:
models will fit better, we would be able to use the time-dependency info

Matrix Profile:
Given a time series sequence, can you find a pattern?
Soln1: Compute pairwise distances between different windows of subsequent data points and only store their minimum values.
So calculate, matrix of n data points and m window sizes.
Then only store the minimum values for each window size.

Causality:
Granger causality: given all the information in the universe U, if adding the information of the features X helps in predicting Y (lesser error), then  X => Y i.e. X helps to predict Y better.

Parametric VAR Tests:
Is adding X helping?
Restricted models:
$$Y_t = γ_0 + \sum_{i=1}^{p}{γ_iY_{t-i}} + e_t$$

Unrestricted models:
$$Y_t = α_0 + \sum_{i=1}^{p}{α_iY_{t-i}} + \sum_{i=1}^{p}{β_iX_{t-i}} + u_t$$
Null hypothesis:
$$∀i, β_i=0 $$