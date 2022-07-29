## 极限

### 极限性质
1. **局部有界性**  
	若$\lim\limits_{x \to x_0} f(x)$存在，则$f(x)$在点$x_0$某去心邻域内有界；
2. **保号性**  
	设$\lim\limits_{x \to x_0} f(x) = A$  
	(1) 若$A > 0$，则$\exists > 0$，当$x \in \mathring{U}(x_0, \delta)$时，$f(x) > 0$；即，$A > 0 \Rightarrow f(x) > 0$。($A < 0$同理)  
	(2) 如果当$x \in \mathring{U}(x_0, \delta)$时，$f(x) \geq 0$，那么$A \geq 0$；即，$f(x) \geq 0 \Rightarrow A \geq 0$。($f(x) \leq 0$同理)  
	<mark>:warning: 这里需要注意：</mark>  
		对于(1): $A \geq 0 \nRightarrow f(x) \geq 0$。经典范例：$f(x)=x$在$\mathring{U}(0, \delta)$中极限$A=0$，而$f(x)$很明显存在小于0的情况。  
		对于(2)：$f(x) > 0 \nRightarrow A > 0$。经典范例：$f(x)=x^2$中$f(x)$在$\mathring{U}(0, \delta)$中大于0，而$A = 0$。所以只可以将结论修改为$f(x) > 0 \Rightarrow A \geq 0$。

