# 计量经济学

因为笔记写在笔记本上，所以这里只梳理要点。期中之后的内容：

## Instrumental variable regression

- Endogeneity and Exogeneity 【L6p3】

- **Two conditions for a valid instrument** 【L6p4】
    - $Corr(Z_i, X_i) \neq 0$
    - $Corr(Z_i, u_i) = 0$

### IV regression with single X and Z

- Two Stage Least Squares (TSLS) 【L6p5】
    - 推导

- Explanation #2 【L6p8】
    - Get the same estimator

- Consistency of TSLS estimator

- Statistical inference
    - In the usual way. In large sample, TSLS estimator approx. to normal. 
    - The OLS standard errors from the second stage regression alone aren’t right. 

### General IV regression model

- Regressors:
    - Endogeneous regressors: $X_k$
    - Exogeneous regressors: $W_r$
    - Instrumental variables: $Z_m$

- Situations
    - Exactly identified: $m=k$
    - Overidentified: $m>k$
    - underidentified: $m<k$

- The IV regression assumptions 【L6p36】
    - $E(u_i|W_{1i},...,W_{ri}) = 0$
    - YXWZ are iid
    - YXWZ have nonzero finite 4th moments
    - The instruments are valid

- Under these assumptions, TSLS and its t-statistic are normally distributed. 

- Checking instrument validity
    - Instrument relevance
        - relevant: at least one of the $\pi$s are nonzero
        - weak: all are either 0 or nearly 0
        - First stage F test
    - Instrument exogeneity
        - **J test of overidentifing restrictions** 【L6p45】

--- 





