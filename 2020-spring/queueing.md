# Queueing models

[Back to OR2](OR2.md)

## General results

$X(t)$: The number of customers in the system at time t

$X_n$: The number of customers left behind by the nth departure. 

$X_n^*$: The number of customers in the system seen by the nth **entry**

$\hat{X}_n$: The number of customers in the system seen by the nth **arrival**

- Arrivals and departures take place one at a time. If the limits exist, then

$$\pi_j = \pi_j^*$$

- **PASTA** (Poisson arrivals see time average): 

$$p_j = \hat{\pi}_j$$

Little's Law
- 对于 system, queue, servers 都成立

## M/M/1/1

modeled as a CTMC on state space {0, 1}.

- Steady distribution: $p_0 = \frac{\mu}{\lambda + \mu}$, $p_1 = \frac{\lambda}{\lambda + \mu}$

- Arrival: $\hat{\pi}_0 = p_0$

- Departure: $\pi_0 = 1$, $\pi_1 = 0$

- Entering: $\pi_0^* = 1$, $\pi_1^* = 0$

## Birth and death process (finite capacity)

Limiting probabilities:

$$p_i = \frac{\rho_i}{\sum_{j=0}^{K} \rho_j}$$

$$\rho_i = \frac{\lambda_0 ... \lambda_{i-1}}{\mu_1 ... \mu_i}$$

之后的模型都是通过生灭过程推出来的，不管s取多少，都是它的特例。

## M/M/1/K

$$\rho_i = \rho^i$$

$$p_i = \frac{1-\rho}{1-\rho^{K+1}} \rho^i, \quad if\ \rho \neq 1$$

$$p_i = \frac{1}{1+K}, \quad if\ \rho = 1$$

### Performance

- Server idleness: $p_0 = \frac{1-\rho}{1-\rho^{K+1}}$

- Blocking probability: $p_K = \frac{1-\rho}{1-\rho^{K+1}} \rho^K$

- Entering: $\pi_i^* = \frac{p_i}{1-p_K}$

- $L = \sum_{i=1}^{K} ip_i$, 
    - if $\rho = 1$, $L = \frac{K}{2}$
    - if $\rho \neq 1$, 注意处理 $\sum_{i=1}^{K} i\rho^i$, 提出一个$\rho$，化为sum的求导。

    $$\frac{\rho}{1-\rho}\frac{1-(K+1)\rho^K+K\rho^{K+1}}{1-\rho_{K+1}}$$

- $W$, little's law

- $W$ for enters: $W' = \frac{L}{\lambda (1-p_K)}$

## M/M/s/K

$$\rho = \frac{\lambda}{s\mu}$$

$$p_i = p_0 \rho_i$$

公式就不列了，都是从生灭过程推过来的，难度不大。

## M/M/K/K

Loss system. In this case, $p_i$ is a truncated Poisson random variable. 

$$\rho_i = \frac{(\lambda/\mu)^i}{i!}$$

## Birth and death process (infinite capacity)

只有有限的才讲是否stable，之前的有限的K就不需要考虑是否stable了。

- Stable condition: $\sum_{j=0}^{\infty} \rho_j < \infty$

- Limiting distribution: 分母换成加到无穷

## M/M/1

- Stable condition: $\rho < 1$

- Limiting: $p_i = (1-\rho)\rho^i$

### Performance

- Server idleness: $p_0 = 1 - \rho$, busy: $\rho$

- Embedded distribution: $\hat{\pi}_i = p_i$ (PASTA)

- $L = \frac{\rho}{1-\rho}$, 同样注意求和的处理。

- $W = \frac{1}{\mu - \lambda}$

## M/M/s

- Stable condition: $\rho = \frac{\lambda}{s\mu}< 1$

- Limiting: $p_i = p_0 \rho_i$. 具体不写了，与有限的情况类似，也是从生灭过程推。

### Performance

- Probability of waiting: $\sum_{i=s}^{\infty} p_i = \frac{p_s}{1-\rho}$

- Expected number of busy servers: $\frac{\lambda}{\mu}$

- $L = \frac{\lambda}{\mu} + p_s\frac{\rho}{(1-\rho)^2}$

- $W = \frac{L}{\lambda}$

- $W_q = W - \frac{1}{\mu}$

## $M/M/\infty$

Always stable. 

- Limiting: $p_i = \frac{(\lambda/\mu)^i}{i!} e^{-\lambda/\mu}$. 

### Performance

- $L = \frac{\lambda}{\mu}$

- $W = \frac{1}{\mu}$

## M/G/1

- Service time: General distribution
    - First moment: $\tau$
    - Second moment: $s^2$
    - Variance: $\sigma^2 = s^2 - \tau^2$

- $\{X(t)\}$ is not a CTMC. 

- Stability: $\rho = \lambda \tau < 1$

- Server idle: $1-\rho$

### Performance

- $W_q = \frac{\lambda s^2}{2(1-\rho)}$

- $W$, $L_q$, $L$. 

## G/M/1

- Stability: $\rho = \frac{\lambda}{\mu} < 1$

- Key functional equation: $u = \tilde{G}(\mu (1-u))$
    - If $\rho < 1$, a unique solution in (0, 1). 

- Arrival time distribution: $\pi_i^* = (1-\alpha)\alpha^j$

- Limiting: $p_j = \rho \pi_{j-1}^*$, $p_0 = 1 - \rho$. (PASTA not applicable!)

### Performance

- $L = \frac{\rho}{1-\alpha}$

# Queueing Network

## Jackson network

6个假设

Routing matrix

$$\sum_{j=1}^{N} p_{ij} + r_i = 1$$

- Tandem queue 一个接一个的

- Total arrival rate to node j: $a_j = \lambda_j + \sum_{i=1}^{N} a_i p_{ij}$. matrix form:

$$a = \lambda + aP$$

- Stability condition: 
    - $I - P$ is invertible. 
    - $a_i < s_i u_i$

- Limiting: 每个就按单个的M/M/s算。


