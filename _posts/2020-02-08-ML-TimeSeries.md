---
layout:     post
title:      Time Series Analysis
subtitle:   时间序列
date:       2020-02-08
author:     Paul
header-img: img/post-bg-os-metro.jpg
catalog: true
tags:
    - 
---

## Time Series

Trend + Seasonality + Autocorrelation + Noise

#### Metrics

- mse
- mae
- mape

## Preprocessing and Filtering

#### Detrending

- Non-stationality
    - trend-stationary
    - difference-stationary
- Seasonality

'Random walk' model

#### Autocorrelation

ACF 
- detect non-randomness
- identify approporate model if non-random

#### Outliers

#### "Low Pass" filter

Smoothing
- Linear decay
- MA
  
  MA on past + MA on noise:

  https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%204%20-%20S%2BP/S%2BP%20Week%201%20-%20Lesson%203%20-%20Notebook.ipynb

- Exponential Smoothing

  Filter the high frequency spectual

  3 typical approach for smoothing:

  - SES (simple exponential smoothing): no clear trend or seanonality pattern
    $$
    y_{T+1|T} = \alpha y_T + \alpha(1-\alpha) y_{T-1} + ...
    \\ \alpha: \text{smoothing parameter, can be optimized automatically by tools}
    $$

  - Holt
    
    Extend SES with trend

    $$
    y_{t+h|t} = l_t + hb_t \\
    l_t = \alpha y_t + (1-\alpha) (l_{t-1} + b_{t-1}) \\
    b_t = \beta (l_t-l_{t-1})+(1-\beta)b_{t-1} \\
    \alpha: \text{level smoothing parameter} \\
    \beta: \text{trend smoothing parameter}
    $$

    For long-term forecast, forecasting with Holt’s method will increase or decrease indefinitely into the future. In this case, we use the Damped trend method which has a damping parameter 0< ϕ <1 to prevent the forecast “go wild”.

    $$
    y_{t+h|t} = l_t + (\phi + \phi^2 + ... + \phi^h ) b_t \\
    l_t = \alpha y_t + (1-\alpha) (l_{t-1} + \phi b_{t-1}) \\
    b_t = \beta (l_t-l_{t-1})+(1-\beta) \phi b_{t-1} \\
    \alpha: \text{level smoothing parameter} \\
    \beta: \text{trend smoothing parameter} \\
    \phi: \text{damping parameter}  
    $$

  - Holt-Winter
    
    Extends Holt with seasonality

    Additive method: the seasonal variations are roughly constant through the series.
    
    Multiplicative method: the seasonal variations are changing proportionally to the level of the series.


## AR

PACF

$$
m_t = \beta_0  + \beta_1 m_{t-1} + ... + \beta_p m_{t-p} + \epsilon_t \\
\beta : \text{PACF}
$$

Use PACF to determine p.

## MA

MA(q)
$$
f_t = \mu + \phi_1\epsilon_{t-1} + ... +\phi_q\epsilon_{t-q} + \epsilon_t \\
\epsilon \ \tilde{} \ N(\mu,\delta)
$$

Use ACF to check non-randomness and determine q:

https://www.youtube.com/watch?v=_tgB-ri9-8c

## ARMA

ARMA(1,1):
$$
l_t = \beta_0  + \beta_1 l_{t-1} + \phi_1\epsilon_{t-1} + \epsilon_t
$$

## ARCH

AR + Seasonality

Var(error) is conditionally changing

## ARIMA

AR MA ARMA: for stationary time series

ARMA + Trend

## SARIMA (Seasonal ARIMA)

ARMA + Trend + Seasonality

https://www.youtube.com/watch?v=WjeGUs6mzXg

![convolution-vs-cross-correlation](/img/post-ml-sarima.png)

## White Noise - not predictable

1. Mean = 0
2. std. deviation = constant
3. CORR between lags = 0

$$
y_t = signal + noise 
$$

if residuals = or ~= white noise, the model is good

#### Testing for white noise

1. visual test
2. global vs. local check
3. check ACF

## Stationary

1. Mean = constant
2. std. deviation = constant
3. no seasonality

#### Testing for Stationary

1. visual test
2. global vs. local check
3. use (ADF) augmented dickey-fuller


## 参考资料

#### 已看文章

#### 待看文章
