# 线性代数

## 四个基本子空间

Suppose matrix A is m*n. 

- Column space: $C(A)$ in $R^m$ dimension $r$
- Null space: $N(A)$ in $R^n$ dimension $n-r$
- Row space: $C(A^T)$ in $R^n$ dimension $r$
- Null space of $A^T$: $N(A^T)$ in $R^m$ dimension $m-r$

列空间即列向量的线性组合。

$Ax=b$ 即是看向量b是否在在A的列空间上。不总有解。

零空间是 $Ax=0$ 的解。

当行向量线性无关时，它们是行空间的一组基。

null space of $A^T$ $\perp$ column space of $A$

null space of $A$ $\perp$ row space of $A$

## 投影

$$P = \frac{aa^T}{a^Ta}$$
$$projection = Pb$$

任何向量乘以投影矩阵P都会落在P的列空间中。P的列空间经过直线a。

$$P^T=P$$
$$P^2=P$$

矩阵形式：

$$P = A(A^TA)^{-1}A^T$$

If b in column space: $Pb = b$

If b $\perp$ column space: $Pb = 0$

## 最小二乘

$$A^TA\hat{x} = A^Tb$$
$$P = A\hat{x}$$

其中 $\hat{x}$ 为 $y = C + Dt$ 中的C与D。

Ax不可能等于b（即点不在一条直线上），所以让Ax等于p，p就是b在A的列空间上的投影。

## 正交矩阵

Orthogonal

$$Q^TQ=I$$

在Q的列空间的投影：

$$P = Q(Q^TQ)^{-1}Q^T = QQ^T$$
$$\hat{x} = Q^Tb$$

### Graham-Schmidt

$$A = a$$
$$B = b - \frac{A^Tb}{A^TA}A$$
$$C = c - \frac{A^Tc}{A^TA}A - \frac{B^Tc}{B^TB}B$$

$q_1, q_2, q_3$ 为它们单位化后的。

## 克拉默法则

代数余子式

## 对角化

$$A = S\Lambda S^{-1}$$

S为A的特征向量的组合。

## 对称矩阵

谱分解

Every symmetric matrix is a combination of perpendicular projection matrices. 

主元的符号和特征根的符号一样。即正数主元的个数和正数特征根的个数相等。

正定矩阵是一种特殊的对称矩阵。

## 正定矩阵

- All eigenvalues are positive
- All pivots are positive
- All sub-determinants are positive

## 傅里叶

### Fourier Series

pass

### Fast Fourier Transformation

$$F_n = \begin{bmatrix}
1 & 1 & 1 & ...\\
1 & w & w^2 & ...\\
1 & w^2 & w^4 & ...\\
... & ... & ... & ...
\end{bmatrix}$$

快速分解，64 - 32 - 16 ... 2 - 1。所以时间为 $n\log{n}$，比原先的 $n^2$ 提升许多。

## 复矩阵

内积为 $\bar{a}^T a$

## 相似矩阵

$$B = M^{-1} AM$$

则A与B相似。相似矩阵有相同的特征根。

## 若尔当标准型

当有相同特征根时。

small family：$\begin{bmatrix} 4 & 0\\ 0 & 4 \end{bmatrix}$ 两边怎么乘，都只有它一个。

big family：$\begin{bmatrix} 4 & 1\\ 0 & 4 \end{bmatrix}$ Jordan form

## 奇异值分解

Singular Value Decomposition (SVD)

$$A = U \Sigma V^T$$

证

$$A^TA = V \begin{bmatrix} \sigma_1^2 & 0\\ 0 & ... \end{bmatrix} V^T$$

$\Sigma$ 里的东西是矩阵 $A^TA$ 的特征根的开根号。$V$ 是 $A^TA$ 的特征向量组合，$U$ 则是 $AA^T$ 的特征向量组合。

## 线性变换和基变换

## 左右逆和伪逆

$A^+$ 表示A的伪逆（A可以是m*n），根据奇异值分解：

$$A = U \Sigma V^T$$

则

$$A^+ = V \Sigma^+ U^T$$


---

[Back to top](#线性代数)
