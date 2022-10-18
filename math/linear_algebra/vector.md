## 向量 (难点)

### 大纲
1. 线性表示
2. 相关、无关
3. 秩（向量组、矩阵）
4. 正交矩阵

---


### 向量的运算
基本运算：略

向量的内积：  
$设\alpha = (a_{1}\ a_{2}\ \cdots\ a_{n})^{T}，\beta = (b_{1}\ b_{2} \cdots b_{n})^{T}$  
则$\alpha$和$\beta$的内积$\alpha^{T}\beta$或$(\alpha, \beta) = a_{1}b{1} + a_{2}b_{2} + \cdots + a_{n}b_{n}$，<rm>内积是一个数</rm>，<bm>内积为0，则称$\alpha$和$\beta$正交。</bm>

向量的长度：
向量$\alpha=(a_{1}\ a_{2}\ \cdots\ a_{n})$，则$\sqrt{a_{1}^{2} + a_{2}^{2} + \cdots + a_{n}^{2}}$为向量$\alpha$的长度。

<bm>**向量组等价**：两个向量组可以互相线性表出。</bm>

---


### 线性表示
线性组合：$k_{1}\alpha_{1} + k_{2}\alpha_{2} + \cdots + k_{m}\alpha_{m}$是向量组$\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}$的<bm>一个</bm>线性组合。

线性表示：若存在一组数$k$使得n维向量$\beta = k_{1}\alpha_{1} + k_{2}\alpha_{2} + \cdots + k_{m}\alpha_{m}$($\alpha$也是n维向量)，则$\beta$可以由$\alpha$向量组线性表示。

:fire:线性表示的充要条件：  
<rm>$\beta$可以由$\alpha$线性表示</rm>$\Longleftrightarrow$<rm>$r([\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}]) = r([\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}\ |\ \beta])$</rm>$\Longleftrightarrow$<rm>非齐次方程组$[\alpha_{1}x_{1} \quad \alpha_{2}x_{2} \ \cdots\ \alpha_{m}x_{m}] = \beta$有解</rm>

<plain>

当$r([\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}]) = r([\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}\ |\ \beta])$，即非齐次方程组$[\alpha_{1}x_{1} \quad \alpha_{2}x_{2} \ \cdots\ \alpha_{m}x_{m}] = \beta$有解时，又分两种情况：
- $r([\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}]) < m$，有无穷多解；
- $r([\alpha_{1}\ \alpha_{2} \cdots \alpha_{m}]) = m$，有唯一个解；

</plain>

**线性表出的传递性**：若向量$\alpha$可以由向量组$\beta$线性表出，而向量组$\beta$又可以由向量组$\gamma$线性表出，则$\alpha$可以由$\gamma$线性表出。

**常用求解方法**  
1. 求矩阵的秩与增广矩阵的秩是否相等。

---


### 线性相关
**对定义的理解**  
结合线性表出的定义，$\alpha_{1}, \alpha_{2}, \cdots \alpha_{m}$线性相关是$\beta$为零向量的特殊情况，是对齐次方程组$[\alpha_{1}x_{1}\ \alpha_{2}x_{2}\ \cdots \alpha_{m}x_{m}] = 0$求解的情况，所以$r([\alpha_{1}\ \alpha_{2}\ \cdots \alpha_{m}\ |\ 0])$
必然等于$r([\alpha_{1}\ \alpha_{2}\ \cdots \alpha_{m}])$，也就是说<bm>一定有解。(这也说明了齐次方程组必有解)</bm>

当$r([\alpha_{1}\ \alpha_{2}\ \cdots \alpha_{m}\ |\ 0])$<bm>小于m时，有无穷多解，自然有非零解，</bm>即存在不全为0的$k_{1}\ k_{2}\ \cdots k_{m}$使得$\alpha_{1}k_{1} + \alpha_{2}k_{2} + \cdots + \alpha_{m}k_{m} = \beta$，这时线性相关。

当$r([\alpha_{1}\ \alpha_{2}\ \cdots \alpha_{m}\ |\ 0])$<bm>等于m时，有唯一解，而$\beta=0$，所以只能有唯一的零解。</bm>，这是线性无关。

<plain>

- 包含零向量的向量组一定线性相关。
- 包含相等的、坐标成比例的向量的向量组一定线性相关。
- 向量个数大于维数的向量组一定线性相关。
- 若向量组线性相关，增加向量个数得到的新的向量组一定线性相关。
- 若向量组**线性无关**，增加向量组的**维数**得到的新的向量组依然**线性无关**。<bm>(低维无关 $\Rightarrow$ 高维必无关)</bm>
- 若向量组**线性相关**，减少向量组的**维数**得到的新的向量组依然**线性相关**。<bm>(高维相关 $\Rightarrow$ 低维必相关)</bm>
- 向量组$\alpha_{1}\ \alpha_{2}\ \cdots \alpha_{m}$线性无关，增加一个$\beta$后线性相关，<bm>向量$\beta$可以由$\alpha$线性表示，且表示方式唯一。</bm>

</plain>

**常用求解方法**  
1. 求秩是否小于向量个数。
2. n个n维向量的向量组求对应行列式是否为零。


### Schmidt正交化(正交规范化方法)
设$\alpha_{1}\ \alpha_{2}\ \alpha_{3}$线性无关。

步骤一：正交化

令$\beta_{1} = \alpha_{1}$

$\beta_{2} = \alpha_{2} - \frac{(\alpha_{2}, \beta_{1})}{(\beta_{1}, \beta_{1})}\beta_{1}$

$\beta_{3} = \alpha_{3} - \frac{(\alpha_{3}, \beta_{1})}{(\beta_{1}, \beta_{1})}\beta_{1} - \frac{(\alpha_{3}, \beta_{2})}{(\beta_{2}, \beta_{2})}\beta_{2}$

步骤二：单位化

$\gamma_{1} = \frac{\beta_{1}}{|\beta_{1}|}$；
$\gamma_{2} = \frac{\beta_{2}}{|\beta_{2}|}$；
$\gamma_{3} = \frac{\beta_{3}}{|\beta_{3}|}$。

---


### 习题
#### 向量的运算
略

---


#### 线性表示
略

---


#### 线性相关


---



