# 行列式
## 按行展开
### 余子式
### 代数余子式

**引理** n阶行列式,如果i行处元素(i,j)外全为0，则
$$
D=a_{ij}A_{ij}
$$
**证** 经过i+j-2ci次兑换换到(1,1),利用拉普拉斯行列式解

**定理1** 行列式等于任意一行|列各元素与其对应的代数余子式乘积之和，即
$$
D=\sum_{j=1}^{n}a_{ij}A_{ij}=a_{i1}A_{i1}+a_{i_2}A_{i_2}+\cdots+a_{in}A_{in}
$$
**证** 
$$
D=
\begin{vmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{i1} & a_{i_2}& \cdots & a_{in} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}\\
=
\begin{vmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{i1}+0+\cdots+0 & 0+a_{i_2}+\cdots+0& \cdots & 0+0+\cdots+a_{in} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}\\
=
\begin{vmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{i1} & 0& \cdots & 0 \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}+
\begin{vmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    0 & a_{i_2}& \cdots & 0 \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}+\cdots+
\begin{vmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    \vdots & \vdots & \ddots & \vdots \\
    0 & 0& \cdots & a_{in} \\
    \vdots & \vdots & \ddots & \vdots \\
    a_{n1} & a_{n2} & \cdots & a_{nn}
\end{vmatrix}\\
=a_{i1}A_{i1}+a_{i_2}A_{i_2}+\cdots+a_{in}A_{in}
$$
**推论** 一行元素与其他任意行的代数余子式乘积和为0，即
$$
a_{i1}A_{j1}+a_{i_2}A_{j_2}+\cdots+a_{in}A_{jn}=0,i\ne j
$$
**证** 相当于用第i行替代了第j行元素的行列式，线性相关了直接0