---
layout:     post
title:      Time Series Analysis
subtitle:   时间序列
date:       2020-01-31
author:     Paul
header-img: img/post-bg-os-metro.jpg
catalog: true
tags:
    - 
---

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

    





## 参考资料

#### 已看文章

#### 待看文章
