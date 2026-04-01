# Distributed Lag Models in Dynamic Model Time Series Time series data often exhibit delayed effects, where past values of a
variable influence the present. Dynamic models capture these...

### Distributed Lag Models in Dynamic Model Time Series
Time series data often exhibit delayed effects, where past values of a
variable influence the present. Dynamic models capture these
dependencies by incorporating lagged values of explanatory variables.
One important class of dynamic models is the **distributed lag model
(DLM)**, which explicitly accounts for how past values affect the
present over multiple time steps.

### What Are Distributed Lag Models?
A **distributed lag model** assumes that the dependent variable at time
t depends on the current and past values of one or more independent
variables. A simple distributed lag model with one explanatory variable
X_t looks like this:


where:

- Yt is the dependent variable (e.g., sales, temperature, or
  production).
- Xt is an independent variable (e.g., advertising spending, weather
  conditions, or economic indicators).
- k is the maximum lag length.
- βi are the coefficients that determine the impact of each
  lag.
- ϵt is the error term.

If βi values are large for small i and decrease over time, the effect of
Xt decays rapidly. If βi values remain significant over longer lags,
past values of X have a prolonged effect. If some βi values are
negative, the effect of Xt may be oscillatory (e.g., cycles in economic
data).

### Estimating a Distributed Lag Model in Python
Let's illustrate a distributed lag model using the consumer price index
(CPI) with a distributed lag effect.





### Choosing the Number of Lags
We need a way to choose the right number of lags for our model. Too few
lags may miss important delayed effects, while too many can introduce
unnecessary complexity.

#### Methods for Selecting Lags:
- **Information Criteria (AIC/BIC):** Use Akaike Information Criterion
  (AIC) or Bayesian Information Criterion (BIC) to compare models with
  different lag lengths.
- **Significance of Coefficients:** Drop lags with statistically
  insignificant coefficients.
- **Partial Autocorrelation Function (PACF):** Examine PACF to
  determine the number of significant lags.

Using AIC to select the optimal number of lags:


The optimal lag for our CPI data is 1.

### Applications of Distributed Lag Models
Distributed lag models are useful in various fields:

- **Economics:** Modeling the impact of monetary policy changes on
  inflation and unemployment.
- **Marketing:** Understanding how advertising campaigns affect future
  sales.
- **Energy Demand Forecasting:** Estimating the delayed impact of
  temperature changes on electricity consumption.
- **Public Policy:** Measuring how tax changes influence consumer
  spending over time.

Distributed lag models are a framework to see how past values of an
independent variable influence present outcomes. This gives us insights
into delayed relationships and improve forecasting accuracy.
