# 向量
**定义1** n维向量  
n个**有次序**的数所组成的数组
默认为实数域
awaw
在解析几何中，
向量：既有大小又有方向的量
向量的几何形象：可随意平移的有向线段
向量的坐标表示；n个有次序的实数

故可以用几何的辅助对向量关系的理解

故向量空间：类比取定坐标系的点空间-取一组线性无关向量就可以建立向量空间

如三维点直角坐标点空间可以看成取  
(0,0,1)(0,1,0)(1,0,0)  
三个三维向量构成的向量空间


向量组：若干`同维数`的列向量或行向量组成的集合

## 向量的线性表示
**定义2** 向量组的线性组合  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,$\forall \lambda_1,\lambda_2,\cdots,\lambda_n$,表达式
$$
k_1a_1+k_2a_2+\cdots+k_na_n
\int_{-\infty}^{\infty}f(x){\rm d}x
$$
称为A的一个线性组合  

**定义3** 向量由向量组线性表示  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,$\exists\lambda_1,\lambda_2,\cdots,\lambda_n$使得
$$
b=k_1a_1+k_2a_2+\cdots+k_na_n
$$
则b是向量组A的线性组合，b能用A线性表示

**定理1** 向量b能用向量组线性表示  $\Leftrightarrow$r(A)=r(B[A,b])  
**证** 转化为方程$A_{m\times n}k_{n\times 1}=b_{m\times 1}$

## 向量组的线性表示与等价
**定义3** 向量组的线性表示  
设有两个向量组$A:a_1,a_2,\cdots a_m;B:b_1,b_2,\cdots b_n$,若B组中的每一个向量都能用向量组A线性表示，则称向量组B能由向量组A线性表示，

**定义3** 向量组等价  
若向量组A和向量组B能相互线性表示，则称这两个`向量等价`

**定理2** 定义1$\Leftrightarrow R(A)=R(A,B)$  
**证** 转化为矩阵方程$AK=B$,K为系数矩阵,有解的充要条件  

**推论** 定义2$\Leftrightarrow R(A)=R(B)=R(A,B)$

理解：两个向量组秩相等，且本身元素的维数相同`隐含了同维条件`，第二个等号`至关重要`

**定理3** 若B能被A线性表示，则$R(B)\leq R(A)$  
**证** 根据**定理2**，$R(A)=R(A,B)$   
$$
\because R(B)\leq R(A,B)\\
\therefore R(B)\leq R(A)
$$

### 向量组等价的判定
拼在一起求行最简矩阵的秩
`向量组和最大线性无关组是等价向量组`
## 向量组的线性相关与无关
**定义** 线性相关  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,$\exists\lambda_1,\lambda_2,\cdots,\lambda_n$不全为0，使得
$$
k_1a_1+k_2a_2+\cdots+k_na_n=0
$$
则称向量组A线性相关

理解
`至少有一个向量是多余的` ；齐次线性方程组有非0解


**定义** 线性无关  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,当且仅当$\lambda_1=\lambda_2=\cdots=\lambda_n=0$，使得
$$
k_1a_1+k_2a_2+\cdots+k_na_n=0
$$
则称向量组A线性无关

理解：`非线性相关，必无关`；齐次线性方程组有唯一0解

**定理4** 线性相关$\Leftrightarrow R(A)=m$  
线性无关$\Leftrightarrow R(A)<m$
### 判断线性相关7大定理

1 A线性相关$\Leftrightarrow$A中至少有一个$a_i$可由其余n-1个向量线性表示  
**证** 必要性
不妨设$k_i\ne 0$,则
$$
a_i=-(\frac{1}{k_i})(k_1a_1+\cdots+k_{i-1}a_{i-1}+k_{i+1}a_{i+1}+\cdots+k_na_n)
$$
 


**定理5**   
(1)若A线性相关，则$B=(a_{0},A,a_{n+1})$线性相关  
(2) m个n维向量组成的向量组，当m超过维度n时，一定线性相关  
(3)若向量组$a_1,a_2,a_3,\cdots a_m$线性无关，$b,a_1,a_2,a_3,\cdots a_m$线性相关，则b能用$a_1,a_2,a_3,\cdots a_m$`唯一线性`表示  
**证** 均可用**定理4**证明，如(3),根据**定理4**
$$
\because R(A)=m,R(A)\leq R(B)<m+1\\
\therefore R(A)=R(B)=m
$$
$\therefore Ax=b$有唯一解


## 向量组的秩

**定义** 设有向量组$A$，如果在$A$中任意选r个向量$a_1,a_2,\cdots a_r$  
(i) 向量组$A_0:a_1,a_2,\cdots a_r$线性无关  
(ii) 任意r+1个向量组线性相关  
那么称向量组$A_0$是向量组$A$的一个**最大线性无关向量组**，最大线性无关组所含的向量个数r为**向量组的秩**，记作$R_A$

理解：向量组所张成的向量空间的维数  

规定只含0向量的向量组秩为0

**等价定义**  
TODO 等价推论  


**定理6** 矩阵的秩等于它的列向量组的秩也等于它的行向量组的秩
**证** 利用矩阵秩的定义，
TODO 妙  

### 求解
化为行阶梯型矩阵
## 线性方程组解的结构
### 齐次线性方程组
改写为向量方程
$$
Ax=0
$$
**性质1** 若$x=\xi_1,x=\xi_2$为齐次线性方程的两个解，则$x=\xi_1+\xi_2$也是齐次线性方程的解  
**性质2** 若$x=\xi_1$为向量方程$Ax=0$的解，则$x=k\xi_1$也是解

由于$Ax=0$经常解除无穷多个解，那么我们把这无穷多个解的全体组成的集合叫做S`解空间`，如何表示？，用解集的某一最大线性无关组$S_0=\xi_1, \xi_2, \cdots, \xi_t$的任意系数的线性组合来表示  
$$
x= k_1\xi_1+ k_2\xi_2+ \cdots+k_t\xi_t
$$
把$S_0$称为$Ax=0$的基础解系
### 非齐次线性方程组
**性质1** xx
**性质2** xx
### 利用解的结构解决抽象型方程组问题
#### 有解条件判定
求R(A)
#### 解的结构
求R(A)
#### 基础解系
求R(A)→解方程
#### 线性方程解与向量等式系数的关系

## 向量空间
**定义** 向量空间  
n维向量的全体构成的集合$\mathbb{R}^{n}$叫做n维向量空间  
设$V$为n维向量的集合，若集合$V\ne \phi$,且对加法和数乘两种运算都封闭，那么就称集合$V$为向量空间  

子空间：

基和维数：

向量组的秩就是L的维数，向量组的最大无关组就是L的一个基

坐标
自然基

### 基变换公式与坐标变换公式
设过渡矩阵P-肯定是进行列变换锕  
基变换
故AP=B
$$
P=A^{-1}B
$$

**解** 已知A,B求P，思路求A的逆,左乘放行
$$
(A,B)\overset{r}{\sim}(E,P)
$$

坐标变换公式
$$
\begin{bmatrix}
    z_1 \\ z_2 \\ \vdots \\ z_n 
\end{bmatrix}=P^{-1}\begin{bmatrix}
    y_1 \\ y_2 \\ \vdots \\ y_n 
\end{bmatrix}
$$
**解** 已知Y，P求Z，
$$
(P,Y)\overset{r}{\sim}(E,Z)
$$