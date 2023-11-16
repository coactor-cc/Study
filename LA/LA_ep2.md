# 矩阵
## 概念
一个抽象的二维信息`系统信息`表达  

观点1：向量组  
观点2：不能运算但存在关系  

可以用来表示向量，也可以用来表示线性方程组

实体：二维数表
### 向量
#### 行矩阵|行向量
为避免混淆在中间加了,记作
$$
A=\begin{pmatrix} 
    x_1, x_2, \cdots, x_n
\end{pmatrix}
$$

#### 列矩阵|列向量
$$
\begin{pmatrix}
    x_1 \\ x_2 \\ \vdots \\ x_n 
\end{pmatrix}
$$
## 类型
同型矩阵

方阵-对角矩阵$\Lambda$-系数矩阵-单位矩阵E



0矩阵

对于非齐次线性方程组
系数矩阵A
常数项矩阵b
增广矩阵B
## 运算
### =，+  同型矩阵
### 数·乘 同型矩阵
由于矩阵是一个系统的信息，你必须保证内部信息不变  
乘到`每个元素`，矩阵没有定义运算域
$$
kA=\begin{bmatrix}
    ka_{11} & ka_{12} & \cdots & ka_{1n} \\
    ka_{21} & ka_{22} & \cdots & ka_{2n} \\
    \vdots & \vdots & \ddots & \vdots \\
    ka_{n1} & ka_{n2} & \cdots & ka_{nn}
\end{bmatrix}
$$
### 矩阵·矩阵 a×b-b×c

#### `E的矩阵相乘性质`
$$
E_mA_{m\times n}=A_{m\times n}\\
A_{m\times n}E_n=A_{m\times n}\\
$$
#### 特殊 向量内积
$$
V^{\mathsf{T}}V=
\begin{bmatrix} 
    x_1, x_2, \cdots, x_n
\end{bmatrix}
\begin{bmatrix}
    x_1 \\ x_2 \\ \vdots \\ x_n 
\end{bmatrix}

$$
单位向量||V||=1  
正交向量
$$
V^{\mathsf{T}}V=0
$$
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
**证**  已知AB=E
$$
|A|E=A^{*}A=A^{*}EA=A^{*}ABA=|A|BA\\
\because |AB|=|A||B|=|E|\ne 0
\therefore E=BA
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
## 矩阵分块
### 幕
$$
\begin{bmatrix}
    A & 0 \\
    0 & B \\
\end{bmatrix}^{n}
=
\begin{bmatrix}
    A^{n} & 0 \\
    0 & B^{n} \\
\end{bmatrix}
$$
### 分块矩阵的逆
#### 主对角分块
$$
A=\begin{bmatrix}
    A_1  &0  &\cdots&0  \\
    0  &A_2  &\cdots&0  \\
    \vdots&\vdots&\ddots&\vdots\\
    0  &0  &\cdots&A_s   
\end{bmatrix}\\
A^{-1}=
\begin{bmatrix}
    A_1^{-1}  &0  &\cdots&0  \\
    0  &A_2^{-1}  &\cdots&0  \\
    \vdots&\vdots&\ddots&\vdots\\
    0  &0  &\cdots&A_s^{-1}   
\end{bmatrix}
$$
#### 副对角分块  
分块倒序，块内求逆  
$$
A=\begin{bmatrix}
    0    &\cdots&0&A_1  \\
    0    &\cdots&A_2&0 \\
    \vdots&&\vdots&\vdots\\
    A_s    &\cdots&0&0   
\end{bmatrix}\\
A^{-1}=
\begin{bmatrix}
    0    &\cdots&0&A_s^{-1}  \\
    0    &\cdots&A_{s-1}^{-1}&0 \\
    \vdots&&\vdots&\vdots\\
    A_1^{-1}    &\cdots&0&0   
\end{bmatrix}
$$
#### 三角矩阵
主对角：左乘同行，右乘同列，添加负号
副对角：`倒序`+左乘同行，右乘同列，添加负号
$$
X=
\begin{bmatrix}
    A & 0 \\
    C & B \\
\end{bmatrix}\\
X^{-1}=
\begin{bmatrix}
    A^{-1} & 0 \\
    -B^{-1}CA^{-1} & B^{-1} \\
\end{bmatrix}
$$
### 舒尔公式
`当A可逆时`
#### i行变换
$$
\begin{bmatrix}
    E_r & 0 \\
    CA^{-1} & E_{n-r} \\
\end{bmatrix}
\begin{bmatrix}
    A & B \\
    C & D \\
\end{bmatrix}
=
\begin{bmatrix}
    A & B \\
    0 & D-CA^{-1}B \\
\end{bmatrix}
$$
#### ii 列变换
$$
\begin{bmatrix}
    A & B \\
    C & D \\
\end{bmatrix}
\begin{bmatrix}
    E_r & -A^{-1}B \\
    0 & E_{n-r} \\
\end{bmatrix}
=
\begin{bmatrix}
    A & 0 \\
    C & D-CA^{-1}B \\
\end{bmatrix}
$$
#### iii 化为对角
$$
\begin{bmatrix}
    E_r & 0 \\
    CA^{-1} & E_{n-r} \\
\end{bmatrix}
\begin{bmatrix}
    A & B \\
    C & D \\
\end{bmatrix}
\begin{bmatrix}
    E_r & -A^{-1}B \\
    0 & E_{n-r} \\
\end{bmatrix}
=
\begin{bmatrix}
    A & 0 \\
    C & D-CA^{-1}B \\
\end{bmatrix}

$$
