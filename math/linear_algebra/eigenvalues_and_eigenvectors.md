## 特征值和特征向量


## 大纲
### 一、特征值、特征向量
:one: $A\alpha = \lambda\alpha, \quad \alpha \ne 0$

:two: $|\lambda E - A| = 0; \quad (\lambda_{i} E - A)x = 0$

### 二、相似矩阵
$A \sim B; \quad \exist 可逆矩阵P, P^{-1}AP = B$

$A \sim \wedge$

### 三、实对称矩阵
一定可以相似对角化

特征值不同，特征向量相互正交

可用正交矩阵相似对角化

---

## 特征向量和特征值

**矩阵的不同特征值的特征向量必线性无关。**

### 常用性质

设置A为n阶矩阵，特征值$\lambda = (\lambda_{1}, \lambda_{2}, \dots \lambda_{n}), 对应的特征向量为\alpha=(\alpha_{1}, \alpha_{2}, \dots \alpha_{n})$

:one: $\sum \lambda_{i} = \sum a_{ii}$

:two: $\prod\lambda_{i} = |A|$

:three: $A + kE 的特征向量为\lambda + k, 特征向量仍为\alpha$

:four: $A^{m}的特征值为\lambda^{m}，特征向量仍为\alpha$

:five: $A^{T}的特征值为\lambda, 特征向量仍为\alpha$

:six: $A^{*}的特征值为\frac{|A|}{\lambda}, 特征向量仍为\alpha$

:seven: $A^{-1}的特征值为\frac{1}{\lambda}，特征向量仍为\alpha$

---

## 相似矩阵
### 相似矩阵的基本性质
若矩阵$A \sim B$, 则

:one: $A \sim A$

:two: $B \sim A$

:three: $若B \sim C, 则A \sim C$

:four: $\lambda_{A} = \lambda_{B}$

:five: $r(A) = r(B)$

:six: $\sum a_{ii} = \sum b_{ii}$

:seven: $|A| = |B|$

### 补充性质
若矩阵$A \sim B$，则

:one: $A^{T} \sim B^{T}$

:two: $A^{-1} \sim B^{-1}$

:three: $A^{*} \sim B^{*}$

:four: $A^{n} \sim B^{n}$

:five: $A + kE \sim B + kE$

:six: $若A_{1} \sim B_{1}, A_{2} \sim B_{2}则$  
$
\begin{bmatrix}
A_{1} & O			\\
O			& A_{2}	\\
\end{bmatrix}
\sim
\begin{bmatrix}
B_{1} & O			\\
O			& B_{2}	\\
\end{bmatrix}
$

---

## 相似对角化

若$A \sim \wedge, 即P^{-1}AP = \wedge，则称矩阵A可以对角相似化。$

**充分必要条件**: $A \sim \wedge \Longleftrightarrow A有n个线性无关的特征向量$

**对角矩阵的主对角线有A的特征值组成，而P则是由特征值对应的特征向量组成。**

