# 矩阵初等变换与线性方程组
在对矩阵进行了初等变换约束后，矩阵就可以用来计算线性方程组啦
## 初等变换与初等矩阵
单位阵经过一次初等变换得到的矩阵  
### 倍乘
倍乘初等矩阵
$$
E(i(k))=
\begin{bmatrix}
    1  &0  &\cdots&0  \\
    0  &k  &\cdots&0  \\
    \vdots&\vdots&\ddots&\vdots\\
    0  &0  &\cdots&1   
\end{bmatrix}
$$
### 换行
互换初等阵
$$
E(i,j)=
\begin{bmatrix}
    0  &1  &0&\cdots&0  \\
    1  &0  &0&\cdots&0  \\
    0  &0  &1&\cdots&0  \\
    \vdots&\vdots&\vdots&\ddots&\vdots\\
    0  &0  &0&\cdots&1   
\end{bmatrix}
$$
### 倍加
倍加初等阵
$$
E(ij(k))=row_j|col_j+=k(row_i|col_i)\\
=
\begin{bmatrix}
    1  &0  &\cdots&0  \\
    0  &1  &\cdots&0  \\
    \vdots&\vdots&\ddots&\vdots\\
    k  &0  &\cdots&1   
\end{bmatrix}
$$
### 性质
1
初等行变换=左乘初等矩阵；初等列变换=右乘初等矩阵  
2初等矩阵可逆`逆向操作`，且有
$$
E(i(k))^{-1}=E(i(\frac{1}{k}))\\
E(i,j)^{-1}=E(i,j)\\
E(ij(k))^{-1}=E(ij(-k))\\

$$
3方阵A可逆$\Leftrightarrow$A=有限个初等矩阵乘积
## 行最简矩阵F
任意矩阵→行阶梯矩阵→行最简矩阵→标准型F
$$

$$
## 矩阵等价
在解方程意义上等价了  
### 行等价  
将方程组按行看
$$
A\overset{r}{\sim} B
$$
### 列等价
$$
A\overset{c}{\sim} B
$$
### 等价
$$
A\sim B
$$

**定理** 设A,B为m×n的矩阵 
1. $A\overset{r}{\sim} B\Leftrightarrow PA=B$，P为m阶可逆矩阵
2. $A\overset{c}{\sim} B\Leftrightarrow AQ=B$，Q为n阶可逆矩阵
3. $A\sim B\Leftrightarrow PAQ=B$，P为m阶可逆矩阵，Q为n阶可逆矩阵

结论：$A\sim B\Leftrightarrow r(A)=(B)$

**推论** 方阵A可逆$\Leftrightarrow A\overset{r}{\sim} E$  


已知变换前后矩阵A,B，求一个行变换矩阵P的方法
$$
\begin{cases}
PA=B\\
PE=P
\end{cases}
$$
意味着把A变到B的操作能把E变到P，故我们构造(A,E)，然后把A变到B
### 利用初等变换求逆矩阵
A的逆可以看成把A变到E的过程
$$
\because A^{-1}A=E\\
\therefore P=A^{-1}\\
\therefore P(A,E)=(E,P)\\
$$
故构造(A,E),进行变换
### 利用初等行变换解矩阵方程
求AX=B
$$
P(A,B)=(F,PB)
X=PB
$$

