## 矩阵运算

### 大纲
1. 概念、运算
	+ <bm>乘法</bm>, <bul>$\alpha\beta^T \space \alpha^T\beta \space \alpha\alpha^T \space \alpha^T\alpha$</bul>
2. 伴随矩阵、可逆矩阵
	+ <rm>$AA^*=A^*A=|A|E$
3. 初等变换、初等矩阵
4. 分块矩阵
5. 方阵的行列式
	+ <bm>秩</bm>

---

### 概念和运算
$m * n$个数排成如下m行n列的一个<bul>表格</bul>  
$
\begin{bmatrix}
	a_{11} & a_{12} & a_{13} & \cdots & a_{1n} \\
	a_{21} & a_{22} & a_{23} & \cdots & a_{2n} \\
	\vdots & \vdots & \vdots & \ddots & \vdots \\
	a_{m1} & a_{m2} & a_{m3} & \cdots & a_{mn}
\end{bmatrix}
$  
称是一个<rul>$m*n$矩阵</rul>，当m=n时，称为<rul>n阶矩阵</rul>或<rul>n阶方阵</rul>。简记A。  
#### 特殊的几个矩阵
1. <bm>零矩阵</bm>：  
如果一个矩阵的所有元素都是0，即
$$ $$
则称这个矩阵为零矩阵。简记O  
如果$A$$B$都是$m*n$矩阵，称A和B为同型矩阵。  
如果$A$和$B$都是$m*n$矩阵，若$a_{ij}=b_{ij}(\any i=1,2,\cdots,m; j=1,2,\cdots,n)$，称A和B相等，记A=B。  

#### 同型矩阵运算：
+ 加法：$A+B = [a_{ij}+b_{ij}]$
+ 数乘：$kA=[ka_{ij}]$
+ 运算法则：
	- 加法：$ABC$同型  
		<card>
			$A+B=B+A$  
			$(A+B)+C=A+(B+C)=A+B+C$  
			$A+O=O+A=A$  
			$A+(-A)=O$
		</card>
	- 数乘：$AB$同型  
		<card>
			$k(mA)=m(kA)=(km)A$  
			$(k+m)A=kA+mA$  
			$k(A+B)=kA+kB$  
			$1A=A, 0A=O$  
		</card>

#### <rm>矩阵乘法</rm>  
$A=[a_{ij}]_{m×s}$，$B=[b_{ij}]_{s×n}$  
$AB=C=[c_{ij}]_{m×n}$  
$c_{ij} = a_{i1}b_{1j} + a_{i2}b_{2j} + \cdots + a_{is}b_{sj} = \sum\limits^{s}_{k=1}a_{ik}b_{kj}$  
:warning:  
1. <bul>$AB \neq BA$<bul>
2. <bul>$AB=0 \narrow A=0$ 或 $B=0$</bul>
3. <bul>$AB=C, A \neq O \narrow B=C$</bul>

运算法则：  
<card>
	$(AB)C=A(BC)=ABC$  
	<bm>$A(B+C)=AB+AC$  
	$(A+B)C=AC+BC$</bm>  
	$AE=A, EA=A$  
</card>

