# 相似矩阵与二次型
## ~~向量的内积、长度、正交性~~
## 方阵的特征值和特征向量
### 概念
**定义** 设A是n阶矩阵,如果数$\lambda$和n维非0列向量x使
$$
Ax=\lambda x
$$
成立，这样的数$\lambda$称为矩阵的特征值，非零向量x称为A的对应于特征值$\lambda$的特征向量

特征值：使得行列式$|A-\lambda E|=0$的取值

特征向量：齐次线性方程$(A-\lambda E)x=0$的非0解
### 性质
1
$$
\sum_{i=1}^{n}\lambda_i=tr(A)=\sum_{i=1}^{n}a_{ii}=a_{11}+a_{22}+\cdots+a_{ii}
$$
特殊的：$\sum_{i=1}^{n}\frac{|A|}{\lambda_i}=tr(A^{*})=\sum_{i=1}^{n}A_{ii}$  
即$A_{ii}=\frac{\prod_{i=1}^{n}\lambda_i}{\lambda_i}$  
2
$$
\prod_{i=1}^{n}\lambda_i=|A|
$$
### 运算
#### 具体
求解$\lambda$：利用$|A-\lambda E|=0$求解→  
**解** 1元3次方程的问题  
回代求解$\xi$，转化为求齐次线性方程通解问题  
TODO 求解方程定理，速通解向量等技巧  
#### 抽象
利用$\lambda$性质+定义+结论求解
## 相似矩阵
在在不同坐标下对同一变换的描述
$$
B=P^{-1}AP
$$
### 性质
### 相似对角化
### 题目
#### 相似对角化的判定
#### 相似对角化
#### 对称阵的相似对角化
#### 反求参数
## 正交矩阵
由`标准正交基`组成的矩阵   
**定义** 如果n阶矩阵A,满足
$$
A^{\mathsf{T}}A=E(A^{\mathsf{T}}=A^{-1})
$$
则称A为正交矩阵  

分析
$$
\begin{bmatrix}
    a_1^{\mathsf{T}} \\ a_2^{\mathsf{T}} \\ \vdots \\ a_n ^{\mathsf{T}}
\end{bmatrix}
\begin{bmatrix} 
    a_1, a_2, \cdots, a_n
\end{bmatrix}=E\\

a_i^{\mathsf{T}}a_j=
\begin{cases}
1,i=j\\
0,i\ne j
\end{cases}\\
$$
故
$$
||a_i||=1\\
a_i^{\mathsf{T}}\cdot a_j=0
$$

性质  
1
$$
P^{\mathsf{T}}=P^{-1},|P|=\pm 1
$$
2 均为单位向量
$$
\forall\alpha_i\in P ,||\alpha_i||=1
$$
3向量相互垂直
$$
\forall\alpha_i,\alpha_j\in P ,\alpha_i^{\mathsf{T}}\cdot\alpha_j=0
$$
4正交变换线段长度保持不变
$$
y=Px,||y||=\sqrt{y^{\mathsf{T}}y}=\sqrt{x^{\mathsf{T}}P^{\mathsf{T}}Px}=||x||
$$
## 二次型问题
研究n个变量的二次齐次多项式化简问题
### 定义
n元2次齐次多项式
$$
f(x_1,x_2,x_3\cdots x_n)=\sum_{i=1}^{n}a_{ii}x_i^{2}+\cdots
$$
### 矩阵表示
$$
f=x^{\mathsf{T}}Ax
$$
A称为二次型f的矩阵，把f叫做矩阵A的二次型
#### 实对称矩阵
1实对称矩阵必可相似对角化  
2不同$\lambda$的特征向量$\xi$正交
### 标准型
不含交叉项
$$
f=\sum_{i=1}^{n}k_iy_i^{2}
$$
### 规范性
系数只可能是1，-1
$$
f=\sum_{i=1}^{n}(1|-1)y_i^{2}
$$
### 矩阵合同
$$
B=C^{\mathsf{T}}AC
$$

考研仅针对对称矩阵谈合同  
对称矩阵合同也为对称矩阵，且R(A)=R(B)
###  二次型化标准型
寻找`可逆线性变换`
$$
\begin{cases}
x_1=c_{11}y_1+c_{12}y_2+\cdots c_{1n}y_n\\
x_2=c_{22}y_1+c_{22}y_2+\cdots c_{2n}y_n\\
\cdots\\
x_n=c_{nn}y_n+c_{n2}y_2+\cdots c_{nn}y_n\\
\end{cases}
$$
即$x=Cy$,使得
$$
y^{\mathsf{T}}C^{\mathsf{T}}ACy=\sum_{i=3}^{n}k_iy_i^{2}
$$
即寻找C,使得
$$
C^{\mathsf{T}}AC=\Lambda
$$
#### 配方法
不等同于配方，需要一次把一个变量完全的消去


#### 正交变换
利用正交矩阵的优秀性质寻找需要的合同变换矩阵，  
本质，用相似变换矩阵求合同变换矩阵  
正交变换
$$
x=Py
$$
### 惯性定理和正定二次型
正定二次型是指化为标准型后个平方项系数均大于0的二次齐次多项式