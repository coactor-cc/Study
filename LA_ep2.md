# 矩阵
## 概念
一个抽象的二维信息`系统信息`表达  
观点1：向量组  
观点2：不能运算但存在关系  

实体：二维数表

元素

### k阶子式
矩阵内k条横线+k条数线交点元素组成的行列式√  
矩阵用方框套出的行列式×
### 秩
最高阶非0子式的阶数  
线性无关向量的个数

## 类型
同型矩阵

方阵
    对角矩阵
        单位矩阵
行矩阵|行向量
列矩阵|列向量

0矩阵

对于非齐次线性方程组
系数矩阵
常数项矩阵
增广矩阵
## 运算
在`同型矩阵`下：=，+ 数乘
### 数·乘- 同型矩阵下
由于矩阵是一个系统的信息，你必须保证内部信息不变  
乘到`每个元素`，矩阵没有定义运算域
$$
kA=。。。
$$

TODO fix snips bug create a matix $f(x)$  


### 矩阵·矩阵 -在axb bxC的情况下

#### `E的矩阵相乘性质`
$$
E_mA_{m\times n}=A_{m\times n}\\
A_{m\times n}E_n=A_{m\times n}\\
$$
#### 特殊 向量内积
$$

$$
单位向量
正交向量
### 矩阵转置$A^{\mathsf{T}}$
#### 性质
$$
(AB)^{\mathsf{T}}=B^{\mathsf{T}}A^{\mathsf{T}}
$$

### 行列式 -方阵
一种方正的运算，见ep_1
#### 性质
`重要`  
|AB|=|A||B|  
**证** 构造三角行列式→进行行列式变换
$$
|A||B|=
\begin{vmatrix}
    A & 0 \\
    -E & B \\
\end{vmatrix}\\
=
\begin{vmatrix}
    0 & AB \\
    -E & B \\
\end{vmatrix}\\
=|AB|
$$
推论：|AB|=|BA|   
### 矩阵的逆 -方阵
若
$$
AB=E
$$
则称A是可逆矩阵，B是A的逆矩阵，记为$B=A^{-1}$
#### 性质
1可逆具有对称性  
**证**  
TODO ？？  
$$
AB=E\\
A
$$
2定理 A可逆$\Leftrightarrow$|A|≠0  
3
$$
|A^{-1}|=|A|^{-1}
$$
**证** 
$$
AA^{-1}=E\\
|AA^{-1}|=1\\
|A||A^{-1}|=1\\
\because |A|\ne 0\\
\therefore |A^{-1}|=\frac{1}{|A|}=|A|^{-1}
$$

### 伴随-方阵
**定义** 
$$
A^{*}=
\begin{bmatrix}
    A_{11} & A_{21} & \cdots & A_{n1} \\
    A_{12} & A_{22} & \cdots & A_{n2} \\
    \vdots & \vdots & \ddots & \vdots \\
    A_{1n} & A_{2n} & \cdots & A_{nn}
\end{bmatrix}
$$
任何方阵A都有伴随矩阵  
伴随矩阵为代数余子式的`转置`排列
#### 性质
1
$$
AA^{*}=
\begin{vmatrix}
    A \\
\end{vmatrix}
=|A|E
$$
**证**   
$$
AA^{*}=
\begin{bmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix}
\begin{bmatrix}
    A_{11} & A_{21} & \cdots & A_{n1} \\
    A_{12} & A_{22} & \cdots & A_{n2} \\
    \vdots & \vdots & \ddots & \vdots \\
    A_{1n} & A_{2n} & \cdots & A_{nn}
\end{bmatrix}\\
=\begin{bmatrix}
    \sum_{i=1}^{n}a_{1i}A_{1i}&\sum_{i=1}^{n}a_{1i}A_{2i}&\cdots&\sum_{i=1}^{n}a_{1i}A_{ni}\\
    \sum_{i=1}^{n}a_{1i}A_{1i}&\sum_{i=1}^{n}a_{2i}A_{2i}&\cdots&\sum_{i=1}^{n}a_{2i}A_{ni}\\
    \vdots&\vdots&\ddots&\vdots\\
    \sum_{i=1}^{n}a_{ni}A_{1i}&\sum_{i=1}^{n}a_{ni}A_{2i}&\cdots&\sum_{i=1}^{n}a_{ni}A_{ni}
\end{bmatrix}\\
=\begin{bmatrix}
    |A|  &0  &\cdots&0  \\
    0  &|A|  &\cdots&0  \\
    \vdots&\vdots&\ddots&\vdots\\
    0  &0  &\cdots&|A|   
\end{bmatrix}\\
=|A|
\begin{bmatrix}
    1  &0  &\cdots&0  \\
    0  &1  &\cdots&0  \\
    \vdots&\vdots&\ddots&\vdots\\
    0  &0  &\cdots&1   
\end{bmatrix}\\=|A|E
$$
2
$$
\begin{vmatrix}
    A^{*} \\
\end{vmatrix}
=
\begin{vmatrix}
    A \\
\end{vmatrix}^{n-1}
$$
3当|A|≠ 0时，有
$$
A^{*}=
\begin{vmatrix}
    A \\
\end{vmatrix}
A^{-1} 
$$