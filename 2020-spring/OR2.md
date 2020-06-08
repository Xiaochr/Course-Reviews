# 运筹2

## Review

- Parallel system
    - $T = max\{X_1, X_2, ..\}$
    - $P\{T \leq t\} = F^n (t)$

- Series system
    - $T = min\{X_1, X_2, ..\}$
    - $P\{T \leq t\} = 1 - (1 - F(t))^n$

- Expected value

- Conditional expectation
    - $E[X] = E[E[X|Y]]$

- Memoryless
    - Continuous: Exponential distribution
    - Discrete: Geometric

- Poisson, Erlang

---

## Discrete Time Markov Chains

- 根据定义判断是否是DTMC

- 模型设定
    - Transition probability matrix P

- Transient distributions
    - n-step P

- Occupancy times

- Limiting behavior
    - Limiting distribution
    - Stationary distribution
        - Limiting $\rightarrow$ stationary, but stationary not $\rightarrow$ limiting
    - Occupancy distribution

- Irreducible
    - 所有状态都可以互相通达，即 $p_{ij}^{(k)} > 0$
    - Unique stationary distribution
    - Unique occupancy distribution

- Periodicity

- Irreducible + aperiodic + balancing equation = unique limiting distribution

- Cost models
    - $g(T)$
    - Long-run cost rate

- First passage time

---

## Continuous Time Markov Chains

- 根据定义判断是否是CTMC

- 模型设定
    - $P(s+t) = P(s)P(t) = P(t)P(s)$
    - Jump probability $p_{ij}$, different from $P(t)$
    - Transition rate $r_{ij} = r_i p_{ij}$
    - Generator matrix Q

- Poisson process

- Transient analysis
    - 构造一个新的矩阵 $\hat{p}_{ij}$
    - $P(t) = ...\hat{P}^k$

- Occupancy times

- Limiting behavior
    - Limiting distribution
        - If the DTMC is irreducible, then the corresponding CTMC is also irreducible.
        - Rate in = rate out
    - Stationary distribution
    - Occupancy distribution

- Cost models
    - $g(T)$
    - Long-run cost rate

- First passage time


---

## Generalized Markov Models

- 在某些特定的时间点有马尔科夫性

### Renewal process

- $N(t)$ counting process. The number of events during (0, t]
    - If $T_n$ are iid, then $N(t)$ is a renewal process

- Long-run renewal rate

$$\lim_{t \rightarrow \infty} \frac{N(t)}{t} = \frac{1}{\tau}$$

### Cumulative process

- $C(t)$ total net cost incurred over (0, t]
    - $C(t)$ is a cumulative process if $(T_n, C_n)$ is a sequence of iid bivariate random variables. 

- Compound Poisson process
    - If $N(t)$ is a Poisson process, and $C(t)$ is iid

- Long-run cost rate

$$\lim_{t \rightarrow \infty} \frac{C(t)}{t} = \frac{E(C_1)}{E(T_1)}$$

### Semi-Markov process

- Markovian property at every transition epoch $S_n$

- A continuous time Markov chain is an SMP

- Mean first passage time

- Mean inter-visit time

- Occupancy distribution

- Long-run cost rates

---

## Queueing Models

[Click here](queueing.md)

---

## Optimal Design

- Newsvendor model

- Determine optimal number of servers K

- Optimal replacement

- Optimal server allocation

---

## Optimal Control

### Discrete time MDP

- 模型设置
    - State space S
    - Action space A
    - Policy f
    - Transition probability matrix P
    - Cost matrix C(i, a)

- Optimal policy
    - 一些性质
    - Long-run expected cost rate

- Optimization problem

### Semi MDP

- 模型设置
    - State space S
    - Action space A
    - Policy f
    - Transition probability matrix P
    - Cost matrix C(i, a)
    - Duration between two transition w

- Optimal policy

- Optimization problem

---

## 猜测的题型

- 给描述来判断用什么模型
    - DTMC, CTMC, renewal process, cumulative process, SMP, queueing models, queueing network

- Limiting distributions
    - 包括写出 P、R 等矩阵

- First passage time

- Cost model
    - 包括Occupancy times M矩阵。
    - 也涉及到排队模型

- Queueing model
    - Performance: L, W, ...
    - 包括生灭过程的 $\rho$, $p_i$
    - Queueing network

- Optimal design
    - Newsvendor model

- Optimal control
    - MDP
        - 建模
        - 优化
    - SMDP
        - 建模
        - 优化

- 一些概率的证明

---

[Back to top](#运筹2)
