# 多维随机变量及其分布
## 概念
引例  
试验：检测某地区儿童的发育状况  
得样本空间S={儿童1发育状况，儿童2...，儿童3...} 
显然我们需要好几个指标把试验结果用一个随机变量映射会很麻烦，比如你得找出这个品佳指标  
**例** 健康系数[0-1]它有诸多影响因子，之间满足的关系还不知道  
这时候我们不如直观的用一些简单的方法把他们拆分成多个变量   
H(e)用于映射儿童的身高 W(e)用于映射儿童的体重  
用这两个随机变量就可以完成对发育状况的评价了  
当然这两个随机变量可能是相关的，也可能是完全无关的  
直观想，身高和体重可能有内在联系，而经度纬度肯定无关
### n维随机变量|向量
**定义** 定义在同一样本空间上的n个随机变量构成的向量(X,Y,Z,...)
### 联合分布函数
$\mathbb{R^{2}}$→[0,1]
$$
F(x,y)=P\{(X\leq x)\cap(Y\leq y)\}=P\{X\leq x,Y\leq y\}
$$
#### 性质
单调  右连续
有界  
$$
F(-\infty,y)=F(x,-\infty)=F(-\infty,-\infty)=0\\
F(\infty,\infty)=1
$$
非负
### 边缘分布函数
$$
F_X(x)=P\{ X\leq x \}=P\{ X\leq x,Y<+\infty \}=F(x,+\infty)
$$
### 独立性
$$
F(x,y)=F_X(x)\cdot F_Y(y)
$$
## 离散型
### 联合分布律、边缘分布、条件分布
条件=联合/边缘
### 联合分布函数
$$
F(x,y)=P\{ X\leq x,Y\leq y \}=\sum_{D(x,y)}^{}p_D
$$
### 独立性
$$
\forall  p_{\cdot j}p_{i\cdot}=p_{ij}\\
$$
## 连续型
### 联合、边缘、条件概率密度
$$
f_X(x)=\int_{-\infty}^{+\infty}f(x,y){\rm d}y
$$
条件=联合x边缘
$$
f_{X|Y}(x|y)=\frac{f(x,y)}{f_Y(y)}
$$
### 联合、边缘、条件分布函数
联合分布函数
$$
F(x,y)=\int_{-\infty}^{x}\int_{-\infty}^{y}f(u,v){\rm d}u{\rm d}v
$$
边缘分布函数
$$
F_X(x)=F(x,\infty)=\int_{-\infty}^{x}\int_{-\infty}^{+\infty}f(u,v){\rm d}u{\rm d}v
$$
### 独立性
$$
f(x,y)=f_X(x)\cdot f_Y(y)
$$
## 分布
### 二维均匀分布
$$
f(x,y)=
\begin{cases}
\begin{aligned}
&\frac{1}{S_D},&&(x,y)\in D\\
&0,&&其他
\end{aligned}
\end{cases}
$$
## 随机变量函数

TODO 没搞清晰  
### Z=X+Y|X-Y 求f(z)
积分求导交换次序超纲
$$
F(z)=F\{X+Y\leq z\}=\iint_{x+y\leq z}^{}f(x,y){\rm d}\sigma\\
=\int_{-\infty}^{\infty}\int_{-\infty}^{z-x}f(x,y){\rm d}y{\rm d}x\\
=\int_{-\infty}^{\infty}\int_{-\infty}^{z-y}f(x,y){\rm d}x{\rm d}y\\
f(z)=F'(z)=\int_{-\infty}^{\infty}f(z-y,y){\rm d}y=\int_{-\infty}^{\infty}f(x,z-x){\rm d}x
$$
若X,Y相互独立，则
$$
f(x,y)=f_X(x)f_Y(y)\\
f(z)=\int_{-\infty}^{\infty}f_X(z-y)f_Y(y){\rm d}y=\int_{-\infty}^{\infty}f_X(x)f_Y(z-x){\rm d}x
$$
TODO 画出区域  
### Z=XY|Z=X/Y
分布函数法

卷积公式法`X，Y相互独立`
### Z=max{X,Y}|min{X,Y}
