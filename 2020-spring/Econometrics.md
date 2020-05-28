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

## Binary regression

### Linear probability model

- $E(Y) = Pr(Y=1)$

- Interpretation of $\beta_1$: change in probability that $Y=1$ given $\Delta x$. 

- $\hat{Y}$: the predicted probability that $Y=1$ given X. 

- Disadvantages 【L7p9】 can be solved by nonlinear models

### Probit and Logit model

- Probit regression uses the standard normal cdf. 
    - $Pr(Y=1|X) = \Phi (\beta_0 + \beta_1 X)$
    - z-value: $\beta_0 + \beta_1 X$

- Logit regression uses the logistic cdf. 
    - $Pr(Y=1|X) = F (\beta_0 + \beta_1 X)$, $F(x) = \frac{1}{1-e^{-x}}$

- **MLE**
    - In large samples, MLE estimators are consistent, normally distributed and (asymptotically) efficient. 
    - Probit MLE with no X 【L7p29】

- Measures of fit
    - The fraction correctly predicted
    - **Pseudo-$R^2$**: measures the **improvement** in the value of the log likelihood, relative to having no X. **越大越好**

$$\text{pseudo-}R^2 = 1 - \frac{ln L(f_{probit}^{max})}{ln L(f_{Bernoulli}^{max})}$$

--- 

## Panel data regression

- Why are panel data useful? 【L8p4】

$$Y_{it} = \beta_0 + \beta_1 X_{it} + \beta_2 Z_i + u_{it}$$

- Z doesn't change overtime, but not observable. Omitted variable bias. Can be eliminated by panel data regression. 

### Fixed effects form

$$Y_{it} = \alpha_i + \beta_1 X_{it} + u_{it}, \quad \alpha_i = \beta_0 + \beta_2 Z_i$$

- Three situations 【L8p18】
    - If $\alpha_i = \alpha_j$ and $\beta_i = \beta_j$, use pooled OLS. 
    - If $\alpha_i \neq \alpha_j$ and $\beta_i = \beta_j$, fixed effects/random effects
    - If $\alpha_i \neq \alpha_j$ and $\beta_i \neq \beta_j$, variable coefficients model

### Binary form

$$Y_{it} = \beta_0 + \beta_1 X_{it} + \gamma_1 D1_i + \gamma_2 D2_i + ... + u_{it}$$

- Leave out D3, dummy variable trap

### Fixed effects estimation

Three estimation methods:

- "n-1 binary regressors" OLS
    - Only practical when $n$ isn't too big. 

- "Entity-demeaned" OLS

$$\tilde{Y}_{it} = \beta_1 \tilde{X}_{it} + \tilde{u}_{it}$$

$$\tilde{Y}_{it} = Y_{it} - \frac{1}{T} \sum_{i=1}^{T} Y_{it}, \quad \tilde{X}_{it}..., \quad \tilde{u}_{it}...$$

- "Changes" sepcification, without an intercept(only works for $T=2$)

### Time fixed effects

$$Y_{it} = \beta_0 + \beta_1 X_{it} + \beta_2 Z_i + \beta_3 S_t + u_{it}$$

- Time fixed effects only
    - Similar to the fixed effects. 

- Both entity and time effects

$$Y_{it} = \alpha_i + \beta_1 X_{it} + \lambda_t + u_{it}$$

- **Assumptions** for panel data 【L8p35】
    - ...Assumption #5 【L8p39】
    - If Assumption #5 fails, OLS $\beta_1$ will still be unbiased and consistent, but SE will be wrong. Understate the true uncertainty. 

- **Standard errors**

- Limitations of Panel data regression 【L8p62】

---




