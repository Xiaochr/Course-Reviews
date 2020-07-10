# 概率论与数理统计

- Statistics
    - Descriptive Statistics
        - Sampling and Surveys
        - Visual Displays
        - Numerical Summaries
        - Probability Models
    - Inferential Statistics
        - Estimating Parameters
        - Testing Hypothesis
        - Regression and Trends
        - Quality Control

# Descriptive Statistics

## Chebyshev's Theorem

For any population, the percentage of the observations that lie within k standard deviations of the mean must be at least $100(1-\frac{1}{k^2})$

- So $\mu \pm 2\sigma$: 75%
- $\mu \pm 3\sigma$: 88.9%

## Empirical Rule

For normal distributions:

- 68.26% will lie within $\mu \pm \sigma$
- 95.44% will lie within $\mu \pm 2\sigma$
- 99.73% will lie within $\mu \pm 3\sigma$

## Sampling Distribution

Let $X_1, X_2,...,X_n$ be a random sample from a distribution with mean value $\mu$ and standard deviation $\sigma$. Then

- $E(\bar{X}) = \mu_{\bar{X}} = \mu$

- $V(\bar{X}) = \sigma_{\bar{X}}^2 = \frac{\sigma^2}{n}$

## Central Limit Theorem(CLT)

Let $X_1, X_2,...,X_n$ be a random sample from a distribution with mean value $\mu$ and standard deviation $\sigma$. Then in the limit as $n \rightarrow \infin$, the standard version of $\bar{X}$ and $T_0$ have the standard normal distribution. 

$$lim_{n \rightarrow \infin}P(\frac{\bar{X}-\mu}{\sigma/\sqrt{n}} \leq z) = P(Z \leq z) = \Phi(z)$$

and

$$lim_{n \rightarrow \infin}P(\frac{T_0-n\mu}{\sqrt{n}\sigma} \leq z) = P(Z \leq z) = \Phi(z)$$

If $n > 30$, the CLT can be used. 

## Law of Large Numbers(LLN)

Let $X_1, X_2,...,X_n$ be a random sample from a distribution with mean value $\mu$ and standard deviation $\sigma$, then $\bar{X}$ converges to $\mu$

1. In mean square: $E[(\bar{X}-\mu)]^2 \rightarrow 0$ as $n \rightarrow \infin$

2. In probability: $P(|\bar{X}-\mu| \geq \epsilon) \rightarrow 0$ as $n \rightarrow \infin$ for any $\epsilon > 0$

# Probability

## The Law of Large Numbers

As the number of trials increases, any empirical probability approaches its theoretical limit. 

## Bayes Theorem

$$P(B|A) = \frac{P(A|B)P(B)}{P(A)}$$

If $P(A)$ is not given:

$$P(B|A) = \frac{P(A|B)P(B)}{P(A|B)P(B)+P(A|B')P(B')}$$

## Moments

Sometimes the expected values of integer powers of $X$ and $X-\mu$ are called **Moments**. Expected values of powers of $X$ are called **moments about 0** and the powers of $X-\mu$ are called **moments about mean**. 

For example, $E[(X-\mu)^3]$ is the third moment about the mean. 

### Moment Generating Function

$$M_X(t) = E(e^{tX}) = \Sigma_{x \in D}e^{tx}p(x)$$

- If the mgf exists and is the same for two distributions, then the two distributions are the same. 

- If mgf exists, 

$$E(X^r) = M_X^{(r)}(0)$$

- Poisson moment generating function is $M_X(t) = e^{\lambda(e^t - 1)}$

## Normal Approximation to the Binormial

$$P(X \leq x) = B(x;n,p) \approx \Phi(\frac{x+0.5-np}{\sqrt{npq}})$$

In practice, the approximation is adequate provided that both $np \geq 10$ and $nq \geq 10$. 

## Normal Approximation to the Poisson

with $\mu = \lambda$ and $\sigma = \sqrt{\lambda}$

# Inferential Statistics

## Point Estimation

### Consistancy

A consistent estimator converges toward the parameter being estimated as the sample size increases. 

### Bias

An estimator is unbiased if its expected value is the parameter being estimated.

$$MSE = E[(\hat{\theta}-\theta)^2] = V(\hat{\theta}) + [E(\hat{\theta}) - \theta]^2 \\= VarianceOfEstimator + (bias)^2$$

#### Unbiased Estimators

A point estimator $\hat{\theta}$ is said to be unbiased of $\theta$ if $E(\hat{\theta}) = \theta$ for every possible value of $\theta$. If $\hat{\theta}$ is not unbiased, the difference $E(\hat{\theta}) - \theta$ is called the bias of $\hat{\theta}$. 

### Efficiency

Among all estimators that are unbiased, choose the one that has minimum variance. The resulting $\hat{\theta}$ is called the **minimum variance unbiased estimator (MVUE)** of $\theta$. 

Let T be an unbiased estimator of $\theta$. The ratio of the lower bound to the variance of T is its efficiency. Then T is said to be **efficient** if it reaches the Cramer-Rao lower bound (the efficiency is 1). 

### Methods of Point Estimation

#### The Method of Moments

Let $X_1,...,X_n$ be a random sample from a pmf or pdf $f(x)$. The kth population moment is $E(X^k)$ and the kth sample moment is $\frac{1}{n}\Sigma_{i=1}^nX^k_i$.

The moment estimators $\hat{\theta}_1,...,\hat{\theta}_m$ is obtained by equating first m sample moments to the corresponding first m population moments. 

#### Maximum Likelihood Estimation

The maximum likelihood estimates $\hat{\theta}_1,...,\hat{\theta}_m$ are those values of the $\theta_i$'s that maximize the likelihood function, so that

$$f(x_1,...,x_n;\hat{\theta}_1,...,\hat{\theta}_m) \geq f(x_1,...,x_n;\theta_1,...,\theta_m)$$

- Invariance Principle of MLE
    - 变换不变原则

- Large Sample Properties of MLE
    - Under very general conditions, when the sample size is large, the MLE $\hat{\theta}$ is approximately the MVUE of $\theta$. 

## Confidence Intervals

A $100(1-\alpha)\%$ confidence interval for the mean $\mu$ of a normal population when the value of $\sigma$ is known:

$$\bar{x} \pm z_{\alpha / 2}\frac{\sigma}{\sqrt{n}}$$

Confidence level is $1-\alpha$. 

The sample size n necessary to ensure an interval width w: 

$$n = (2z_{\alpha / 2} \frac{\sigma}{w})^2$$

### Large Sample CI

If n is sufficiently large, the standardized variable $Z = \frac{\bar{X}-\mu}{S/\sqrt{n}}$ has approximately a standard normal distribution. This implies that

$$\bar{x} \pm z_{\alpha / 2}\frac{s}{\sqrt{n}}$$

is large sample CI for $\mu$ with confidence level approximately $100(1-\alpha)\%$. 

Generally, $n > 40$ will be sufficient. 

### Student's t distribution

Use the *Student's t distribution* instead of the normal when the population is normal but $\sigma$ is unknown and the sample size is small. 

$$\bar{x} \pm t_{\alpha / 2, n-1}\frac{s}{\sqrt{n}}$$

### Prediction Interval

$$\bar{x} \pm t_{\alpha / 2, n-1} s\sqrt{1+\frac{1}{n}}$$

### Bootstrap

- parametric: 已知一个pdf $f(x;\theta)$ 和一份数据，用这个数据得到的 $\hat{\theta}$ 代入pdf，于是有了一个分布，可以用计算机得到更多份数据，用更多份数据中的 $\hat{\theta}$ 算。

- nonparametric: 和parametric一样的方法，用计算机得到一堆数据，从每份数据里都得出想要的那个统计量，按顺序排列，就可以得到区间。

## Hypothesis

The P-value is the smallest significance level $\alpha$ at which the null hypothesis can be rejected. (Observed Significance Level (OSL))

## ANOVA

### Single factor ANOVA

- Notations
    - The treatment sum of squares: SSTr
    - Error sum of squares: SSE
    - Mean square for treatments: MSTr
    - Mean square for error: MSE
    - SST = SSTr + SSE

- F-test
    - F = MSTr/MSE
    - $H_0$: $\mu$都相等
    - 如果$\mu$差别不大，F值接近1；如果$\mu$差别很大，则F值应远大于1。

- ANOVA table

- Multiple comparisons in ANOVA
    - Tukey's procedure
    - 画横线

### Two-factor ANOVA

- Notations
    - SST
    - SSA
    - SSB
    - SSE

# Linear Regression

...

# Goodness-of-Fit Tests

- GOF
    - observed
    - expected

$$\chi^2 = \sum \frac{(\text{observed} - \text{expected})^2}{\text{expected}}$$

- Contingency tables

---

[Back to top](#概率论与数理统计)


