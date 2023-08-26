# 随机变量及其分布
## 概念
### 随机变量
#### 定义
**定义** X(e)是定义在样本空间S={e}上的单值实值函数。则称X=X(e)为随机变量  

定义域$D\subset S$，值域 $\subset\mathbb{R}$
#### 概率计算
$$
\{X=2\}=A=\{e|X(e)=2\}\\
P\{X=2\}=P(A)=\sum_{i=1}^{n}P(\{e_i\})
$$
**将样本点划分映射到数值,故数值组算一组互斥事件**  
$$
P\{ X=1,2 \}=P\{ X=1\cup X=2 \}= P\{ X=2 \}+P\{ X=1 \}
$$
故可以定义
TODO ???  
$$
P\{X<2\}=P{}
$$
### 随机变量分布
随机变量定义域和值域的映射关系？？？
### 分布率和概率密度
描述随机变量分布的工具  
是某一随机变量值→概率`函数`值的映射
### 分布函数
描述随机变量分布的另一工具  
自变量为x≤k`事件`，因变量为概率`函数`值  
本质，$\mathbb{R}$→S→[0-1]
$$
F(x)=P\{X\leq x\}
$$
#### 用分布函数计算事件概率
我们定义
$$
F(a-0)=\lim_{x\rightarrow a^{-}}F(a)
$$
则有  
P{X≤a}=F(a)  
P{X<a}=F(a-0)  
P{X=a}=F(a)-F(a-0)  
P{X>a}=1-P(X≤a)=1-F(a)  
P{X≥a}=1-P(X<a)=1-F(a-0) 

P(a<X≤b)=F(b)-F(a)  
P{a≤X≤b}=F(b)-F(a-0)  
P{a<X<b}=F(b-0)-F(a)  
P{a≤X<b}=F(b-0)-F(a-0)  
**证** 
$$
\begin{aligned}
P\{x_1<X\leq x_2\}&=P\{ X>x_1\cap X\leq x_2 \}\\
&=P\{ \overline{X\leq x_1} \cap X\leq x_2\}\\
&=P\{ X\leq x_2 \}-P\{ X\leq x_1\cap X\leq x_2 \}\\
\because& x_1<x_2\\
\therefore& \{ X\leq x_1 \}\subset\{ X\leq x_2 \}\\
\therefore& P\{ X\leq x_1\cap X\leq x_2 \}=P\{ X\leq x_1 \}\\
&=F(x_2)-F(x_1)
\end{aligned}
$$

## 离散型随机变量
通常就将有限个点映射到整数了1，2，3，4，5  
将数列化为离散型随机变量X的分布率
### 分布率
概率1以一定的规律分布在各个可能的值上  
P{X=k}=pk,k=1,2,3,4...
$$
\sum_kp_k=1
$$
#### 表格形式
|X| $x_1$ | $x_2$ | $x_3$ | ... |
|---|---|---|---|---|
|P| $p_1$ | $p_2$ | $p_3$ | ... |
#### 矩阵形式
\begin{bmatrix}
    $1 & $2 & $3 \\
    $4 & $5 & $6 \\
    $7 & $8 & $9 \\
\end{bmatrix}

TODO matix  
### 分布函数
$$
F(x)=P\{ X\leq x \}=\sum_{x_i\leq x}P\{X=x_i\}
$$
### 伯努利试验|伯努利概型
**定义** 试验E只有两个结果S={$e_1$，$e_2$}，  
P(\{$e_2$\})=p,P(\{$e_1$\})=1-p  

n重伯努利试验，E独立重复进行n次  
n重伯努利试验的样本空间S={$e_1$$e_2$...$e_1$`(n个)`，$e_2$$e_2$...$e_1$，...}

### 0-1分布B(1,p)
伯努利试验引出的分布律  
将伯努利试验结果用伯努利计数变量X描述    
X(S)：{X=1}→$e_2$,{X=0}→$e_1$ 得分布律
$$
P\{X=k\}=p^{k}(1-p)^{1-k},k=0,1
$$ 
### 二项分布B(n,p)
n重伯努利试验`(概率模型)`引出的分布率  
用随机变量X`伯努利计数变量`，来描述n重伯努利试验中**结果$e_2$出现的次数**，  
不妨设n=3，则有   
X(S):{X=1}→{$e_1$$e_2$$e_2$,$e_2$$e_1$$e_2$,$e_2$$e_2$$e_1$}，  
{X=2}→{$e_1$$e_1$$e_2$,$e_2$$e_1$$e_2$,$e_2$$e_2$$e_2$$e_1$}  
...  
得分布律
$$  
P\{ X=k \}={\rm C}_n^kp^k(1-p)^{n-k},k=0,1,2,\cdots ,n
$$
### 几何分布G(p)
n重伯努利试验引出的分布率  
X表示n重伯努利试验**首次出现结果$e_2$的试验次数**

$$  
P\{ X=k \}=(1-p)^{k-1}p
$$
## 泊松分布P($\lambda$)
n→$\infty$时n重伯努利试验引出的分布？  
X表示n重伯努利试验**结果$e_2$出现的次数**  
**推导** 假定伯努利试验中事件发生概率与事件1/n成正比`类平均分布`，记为$\frac{\lambda}{n}$，则
$$
\begin{aligned}
\lim_{n\rightarrow \infty}P\{ X=k \}&=C_n^k(\frac{\lambda}{n})^k(1-\frac{\lambda}{n})^{n-k}\\
&=\lim_{n\rightarrow \infty}\frac{n(n-1)\cdots(n-k+1)}{k!n^{k}}\lambda^{k}\cdot(1-\frac{\lambda}{n})^{n}\cdot(1-\frac{\lambda}{n})^{-k}\\
&=\frac{\lambda^{k}}{k!}\cdot\lim_{n\rightarrow \infty}(1-\frac{\lambda}{n})^{n}\cdot(1-\frac{\lambda}{n})^{-k}\\
&=\frac{\lambda^{k}}{k!}\cdot{\rm e}^{\lim_{n\rightarrow \infty}n\cdot(-\frac{\lambda}{n})}\cdot 1\\
&=\frac{\lambda^{k}{\rm e}^{-\lambda}}{k!}
\end{aligned}
$$

泊松过程中，  

X~P($\lambda t$)

## 连续型随机变量
### 概率密度函数
由分布函数定义出来？？？，并不是f(x)=P{X=k}这个就全为0了  

分布函数的导函数-相当于分布函数的斜率
$$
F(x)=\int_{-\infty}^{x}f(x){\rm d}x
$$
#### 性质
1.f(x)>0  
2.面积=1  
3.P{a<X≤b}=$\int_{x_1}^{x_2}f(x){\rm d}x$  
4.f(x)若连续，则F'(x)=f(x)  
$$
f(x)=\lim_{\Delta x\rightarrow 0^{+}}
\frac{F(x+\Delta x)-F(x)}{\Delta x}\\
=\lim_{\Delta x\rightarrow 0^{+}}
\frac{P\{ x<X\leq x+\Delta x \}}{\Delta x}\\
\therefore P\{ x<X\leq x+\Delta x \}\approx f(x)\Delta x
$$
### 分布函数
根据高数，可积必**连续**
$$
F(x)=P\{X\leq x\}=\int_{-\infty}^{x}f(t){\rm d}t
$$

### 泊松过程
计数过程：  
#### 条件
独立增量性(independent increments): 在不相交的时间区间里，随机事件发生情况是独立的；   
平稳性(stationary): 在相同时间长度内，随机事件数的分布是一致的.  
普通性 在极小区间内，只能有一个事件发生

（1）平稳性 对于时间段$[t_0,t_0+t)$内发生的呼叫次数只与t有关而与$t_0$无关。而且$\forall t$，记$P_i(t)$为时长t的时间里发生了i次呼叫的概率，那么有$\sum_{i=1}^{n}P_i(t)=1

（2）独立增量性（无后效性） 对于时间段 $[t_0,t_0+t)$内发生的呼叫次数与$t_0$以前发生的事件都相互独立，且在互不相交的时间区间内事件发生是相互独立的

(3)普通性$\lim_{t\rightarrow 0}\frac{P_i(t)}{t}=1$
### 均匀分布U(a,b)
#### 概率密度
$$
f(x)=
\begin{cases}
\begin{aligned}
&\frac{1}{b-a},&&a<x<b,\\
&0,&&\text{其他},
\end{aligned}
\end{cases}
$$
#### 分布函数
$$
F(x)=
\begin{cases}
\begin{aligned}
&0,&&x<a,\\
&\frac{x-a}{b-a},&&a\leq x<b,\\
&1,&&x\geq b,
\end{aligned}

\end{cases}
$$
### 指数分布E($\lambda$)
泊松过程引出的分布  
表示泊松计数过程的时间间隔  
连续型等待分布  
#### 概率密度
推导???
$$
P(\lambda t)=\frac{{\lambda t}^{k}e^{-\lambda t}}{k!}\\
P\{ X=0 \}=
$$
$$
f(x)=
\begin{cases}
\begin{aligned}
&\lambda {\rm e}^{-\lambda x},&&x>0,\\
&0,&&其他,
\end{aligned}
\end{cases}

$$
#### 分布函数
$$
F(x)=
\begin{cases}
\begin{aligned}
&1-e^{-\lambda x},&&x\geq 0,\\
&0,&&其他，
\end{aligned}
\end{cases}
$$
#### 无记忆性
已经工作十小时，再工作10小时，和工作10小时损坏的概率式一样的，利用指数函数的运算性质
### 正态分布N($\mu,\sigma^2$)
#### 概率密度
$$
f(x)=\frac{1}{\sqrt{2\pi}\sigma}{\rm e}^{\frac{-(x-\mu)^{2}}{2\sigma^{2}}}
$$
#### 标准化和标准正态分布N(0,1)
$$
F(x)=P\{X\leq x\}=\Phi(\frac{x-\mu}{\sigma})=\Phi(\frac{x-\mu}{\sqrt{\sigma^{2}}})
$$
#### 性质
$$
X\sim N(\mu_1,\sigma_1^{2}),Y\sim N(\mu_2,\sigma_2^{2})\\
X+Y\sim N(\mu_1+\mu_2,\sigma_1^{2}+\sigma_2^{2})
$$
## 一位`随机变量函数`分布
### 离散到离散√
### 连续到连续
$$
Y=G(X)\\
F_Y(y)=P\{Y\leq y\}=P\{G(X)\leq y\}=\sum_{I_x,G(x)<y}^{}\int_{x_i}^{x_{i+1}}f(x){\rm d}x
$$