# 应用时间序列分析

按照考试内容整理，没有包括所有课程内容。

## Stationary

### 证明stationary 【L2p19】

- **Weak Stationary** ($E(X_t^2)<\infty$)
    - $E(X_t) = \mu$ is a constant, independent of t. 
    - $Cov(X_t, X_{t+k})$ is independent of t for each k. 

- Strong stationary

### ACVF, ACF and PACF

- ACVF
    - $\gamma_0 = var(X_t)$, $|\gamma_k| < \gamma_0$, $\gamma_k = \gamma_{-k}$

- ACF
    - $\rho_0 = 1$, $|\rho_k| < \rho_0$, $\rho_k = \rho_{-k}$

- They are positive semidefinite
    - ACVF of a weak stationary ts iff even and positive semidefinite. 
    - Toeplitz matrix

- PACF 【L2p31】
    - $\Phi_{11} = \rho_1$
    - Calculation: matrix form, Durbin's recursive formula

- Estimation

## MA/AR model

### AR

- Characteristic equation

- Weak stationary: all roots of the characteristic equation lie outside the complex unit circle. 

- ACVF, ACF, PACF
    - AR: PACF截尾

- Yule-Walker equation

- **MA($\infty$) representation**. calculation 【L3p28】

- Estimation 【L3p33】

- **Average length of the stochastic cycle** 会考

### MA

- **Invertibility condition** 会考
    - Iff all the roots of MA characteristic equation $1+\theta_1 z + ... + \theta_q z_q = 0$ lie outside the complex unit circle. 

- ACVF, ACF, PACF 【L3p49】
    - MA: ACF截尾

- **AR($\infty$) representation**. calculation 【L3p46】

## ARMA models

- **Spectral density of ARMA**

- Weak stationary

- Invertibility

- $\Phi(B) = 1 - \Phi_1 B-...$, $\theta(B) = 1 + \theta_1 B +...$

- **MA/AR representation**

- ACVF, ACF 【L3p57】

- Estimation

## ARIMA models

- Identification, fitting, selection

## The fitting of AR model

- Model selection criteria
    - AIC
    - BIC

## Forecasting

### For AR(p)

- One-step, two-step, multi-step

- Forecast error

### For MA(q)

- One-step, two-step, multi-step

- Forecast error 

### For ARMA(p, q)

- 先换成MA表示，然后预测

### For ARIMA(p, d, q)

- Updating forecast

- Example 【L4p26】



## Spectral analysis

- **Spectral density of ARMA** 【L11p6】

## VAR model

- WS (1st and 2nd moments are time-invariant)
    - $E(y_t)$ is constant and time-invariant
    - $E[(y_t - \mu)(y_t - \mu)']$ only depends on k. 

- Covariance matrix, cross-correlation matrix

- Linear dependency: off-diagonal elements

### VAR(1) 【L14p23】

- WS
    - The roots of characteristic equation all lie outside the unit circle. 

$$|\lambda I - \Phi_z| = 0$$

- Covariance matrix calculation. 
    - 拉直矩阵

### VAR(p)

- **WS** 【L14p37】

- **Invertibility**


## Asymptotic theory of AR(1)

- PACF
    - Asymptotic distribution is normal. Compare it to $\pm 1.96/\sqrt{n}$ and decide if it is preferable. 

---

[Back to top](#应用时间序列分析)