# 一元函数积分学
## 原函数与不定积分（求导逆过程）
### 不定积分存在定理
#### 连续函数必有原函数
$$
proof：设f(x)是在区间I上的连续函数,F(x)=\int_a^xf(x){\rm d}x\\
F'(x)=\lim_{\Delta x\rightarrow 0}\frac{F(x+\Delta x)-F(x)}{\Delta x}=\lim_{\Delta x\rightarrow 0}\frac{\int_x^{x+\Delta x}f(t){\rm d}t}{\Delta x}=\lim_{\Delta x\rightarrow 0}\frac{f(\xi)\Delta x}{\Delta x}=\lim_{\xi\rightarrow x}f(\xi)=f(x)
$$
#### 含有第一类间断点和无穷间断点的函数f(x)在包含间断点的区间没有原函数
**结论掌握,待补充**
### 奇偶性分析：
f(x)是以T为周期的连续函数,  
**结论掌握,待补充**
### 周期性分析：
#### 预备定理
$$
如果f(x)是以T为周期的连续函数,它在一个/n个周期上的积分值与起点无关\\
\int_a^{a+T}f(x){\rm d}x=\int_0^{T}f(x){\rm d}x
$$
#### 原函数周期T的充要条件
$$
f(x)是以T为周期的连续函数,\\
\int_a^xf(t){\rm d}t 以T为周期\Leftrightarrow \int_0^{T}f(t){\rm d}t=0
$$
## 定积分(黎曼积分)
### 定义->求数列N项和极限
被积函数，积分变量，积分上下限等概念需要加强
$$
\int_a^bf(x){\rm d}x=\lim_{n\rightarrow\infty}\sum_{i=1}^nf(a+\frac{b-a}{n}i)\frac{b-a}{n}\\
特殊的:
\int_0^1f(x){\rm d}x=\lim_{n\rightarrow\infty}\sum_{i=1}^nf(\frac{i}{n})\frac{1}{n}
$$
### 定积分存在定理_记结论
常义可积(黎曼可积):区间有限,函数有界
#### f(x)在[a,b]连续
#### f(x)在[a,b]单调
#### **f(x)在[a,b]有界且只有有限个间断点**
### 定积分性质
#### 几何性质√
$设a<b,\int_a^b{\rm d}x=b-a$
#### 线性性质√
$\int_a^b[k_1f(x)+k_2g(x)]{\rm d}x=k_1\int_a^bf(x){\rm d}x+k_2\int_a^bg(x){\rm d}x$

#### 可拆性√
$\int_a^bf(x){\rm d}x=\int_a^cf(x){\rm d}x+\int_c^bf(x){\rm d}x$
#### **保号性**※
$在区间[a,b]上,若f(x)\leq g(x),则\int_a^bf(x){\rm d}x\leq \int_a^bg(x){\rm d}x$   
特殊的，积分不等式$|\int_a^bf(x){\rm d}x|\leq \int_a^b|f(x)|{\rm d}x$  
**若f（x）不恒等于0，则严格大于**
$$
证明：\\ 做差法

$$
#### 估值定理※
$M，m分别为f(x)在区间[a,b]上的最大、最小值，有ml\leq \int_a^bf(x){\rm d}x\leq ML$
#### 中值定理※
$设f(x)在区间[a,b]上连续，则至少存在一点\xi,使得\int_a^bf(x){\rm d}x=f(\xi)(b-a)$
$$
证明：因为有界，用定积分保号性->估值定理->\\连续函数，介值定理f(\xi)=\frac{\int_a^b f(x){\rm d}x}{b-a}
$$
#### 奇偶性 ※？——偶倍奇零
不应该放在定积分里，定积分值为常数吖，放在不定积分里或者变限积分里会比较好

## 变限积分（？？积分函数？？）
### 定义（积分上限函数）

### 性质
1. $f(x)在[a,b]可积，则函数F(x)=int_a^bf(x){\rm d}x在[a,b]上连续$
   证明：利用可积的必要条件
2. $f(x)在[a,b]连续，则函数F(x)=int_a^bf(x){\rm d}x在[a,b]上可导$
   
## 反常积分
破环了区间的有限性
### 无穷限的反常积分
e.g.  
$$
S=\int_1^{+\infty}\frac{1}{x^2}{\rm d}x=-\frac{1}{x}\large{|}_1^{+\infty}=1
$$
### 无界函数的反常积分

### 反常积分的敛散性判别（快速做题，利用结论比阶）
1. $\int_1^{+\infty}\frac{1}{x^p}{\rm d}x p>1,收敛；p<1,发散$
2. $\int_0^1\frac{1}{x^p}{\rm d}x p>1,发散；0<p<1,收敛$
![Alt text](image-18.png)  
e.g.2  **重新看**
$$
\int_0^1\frac{\ln x}{x^\alpha}{\rm d}x\\
e.g.3\\
\int_a^{+\infty}\frac{1}{x\ln^px}\\
p\geq 1,收敛，p<1，发散
$$
## 计算
### 基本积分表
### 凑微分法
### 换元积分
### 分部积分
用于形如
1. 幂·（三角、指数）
2. （反三角、对数）·幂
3. （三角）·指数
4. 三角·三角
### 有理函数积分
### 计算细节总结
### 定积分的计算
#### 牛顿——莱布尼兹公式（应用）
有一类间断点需要拆分哦  
有振荡间断点直接用
#### 定积分的换元积分
上下限需要反解  
$$
e.g.\\
\int_a^bf(x){\rm d}x 则积分变量区间x=a->x=b\\
令x=\varphi (t) 则积分变量t的区间怎么来？\\
\varphi(t)=a , \varphi (t)=b ->反解出t的区间，当然上下限位置不能随意换哦不然符号会错
$$
#### 定积分的分部积分
代入上下限  
分部积分法可以逆向使用
#### 定积分的计算性质（奇偶性在定积分计算中的应用）
积分区间对称（不光0点哦），被积函数偶倍ji0
#### 区间再现公式
$$
\begin{gather}
证明\\
\int_a^bf(x){\rm d}x=\\
令x=a+b-t\\
=\int_{t_1}^{t_2}f(a+b-t){\rm d}a+b-t\\
a+b-t_2=b,a+b-t_1=a,得t_1=b，t_2=a\\
=\int_b^af(a+b-t){\rm d}a+b-t\\
=\int_a^bf(a+b-t){\rm d}t\\
\end{gather}
$$ 
#### 华里士公式
## 几何应用
### 面积
#### 直角坐标
$$
S=\int_a^b |f(x)-g(x)|{\rm d}x
$$
#### 参数方程(直角坐标)
难点：如果不知道图像就没法确定围成区域的表达式以及积分的上下限  
1.画图2.计算
$$
\begin{cases}
  x=\varphi_1(\theta)=r\theta-r\sin\theta\\
   y=\varphi_2(\theta)=r(1-\cos\theta ) \\
\end{cases}\\
S=\int_a^b \varphi_2(\varphi_1^{-1}(x)){\rm d}x\\
=\int_{\theta_1}^{\theta_2} \varphi_2(\theta) {\rm d}\varphi_1(\theta)\\

其中\varphi_1(\theta_1)=a，\varphi_1(\theta_2)=b\\
$$
**极坐标系怎么办??**
设想：  
$$
\begin{cases}
  \theta=\varphi_1(t)\\
   r=\varphi_2(t) \\
\end{cases}\\
S=\int_{\theta_1}^{\theta_2} \frac{1}{2}\varphi_2^2(\varphi_1^{-1}(\theta)){\rm d}\theta\\
\int_{t_1}^{t_2}\frac{1}{2} \varphi_2^2(t) {\rm d}\varphi_1(t)
$$
#### 极坐标
扇形微元法
$$
角度极小时，f(\theta_1)\approx f(\theta_2)\\
此时微元面积=扇形面积{\rm d}s=\frac{1}{2}r^2\Delta\theta\\
S=\int_a^b \frac{1}{2}r(\theta)^2{\rm d}\theta
$$

### 旋转体体积
#### 绕x轴 y=c
圆柱环微元法
由于厚度及其薄，前后圆环面积近似相等
圆环面积×Δx近似体积
$$
圆环面积公式S=\pi {r_2}^2-{r_1}^2\\
V_x=\int_a^b \pi |f'^2(x)-g'^2(x)|{\rm d}x\\

其中f'(x)为由旋转轴y=c|0到外边界f(x)的外径\\
g(x)为由旋转轴出发到内边界g'(x)的内径
$$
#### 绕y轴 x=c
薄壳微元法
由于厚度及其薄，外表面积近似内表面积
用表面积×Δx近似体积  
表面积公式=2Πrh
$$
薄壳=\Delta x\times 2\pi r \times h\\
V_y=\int_a^b2\pi r(x) |f(x)-g(x)|{\rm d}x\\
r(x)为从旋转轴出发到积分变量x的半径\\
f(x)-g(x)为薄壳高h
$$
### 函数均值
根据积分中值定理:若y=f(x)~~有界~~连续[a,b]  
$$
\int_a^b f(x){\rm d}x=f(\xi)[b-a]\\
\bar y=f(\xi)=\frac{\int_a^b f(x){\rm d}x}{b-a}
$$
