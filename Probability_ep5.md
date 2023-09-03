# 大数定律和中心极限定理 5'
## 依概率收敛
设随机变量$X$、随机变量序列$\{ X_n|n=1,2,3\cdots \}$如对$\forall \varepsilon >0$有
$$
\lim_{n\rightarrow \infty}P\{ \left\vert X_n-X \right\vert \geq \varepsilon  \}=0\\
or \lim_{n\rightarrow \infty}P\{ \left\vert X_n-X \right\vert < \varepsilon  \}=1
$$
则称随机变量序列$\{ X_n \}$依概率收敛于随机变量$X$，记为
$$
\lim_{n\rightarrow \infty}X_n=X(P)\\
or X_n \overset{P}{\rightarrow} X(n \rightarrow \infty)
$$

**例** 设随机变量$X$,期望$E(X)=\mu$,方差$D(x)=\sigma^{2}$,设随机变量序列$X_1,X_2,\cdots,X_n$与X独立同分布，  
试证：$Y=\frac{2}{n(n+1)}\sum_{i=1}^{n}iX_i\overset{P}{\rightarrow}\mu$  
**证** 
TODO 证明回顾  
## 大数定律
用于计算随机变量序列的算术平均序列$\overline{X}$的概率收敛值
### 切比雪夫大数定律
**定理1** 设$\{ X_n|n=1,2,\cdots,n \}$是**相互独立**的随机变量序列，且方差$D(X_i)$**一致有上界**,则
$$
\frac{1}{n}\sum_{i=1}^{n}X_i\overset{P}{\rightarrow }\frac{1}{n}\sum_{i=1}^{n}E(X_i)
$$

随机变量的算术平均依概率收敛于变量期望的算术平均
### 伯努利大数定律▲
**定理** 设$f_A$是n次独立重复试验中事件A发生的次数，$P$是事件A在每次试验中发生的概率，则有
$$
\lim_{n\rightarrow \infty}P\{ \left\vert \frac{f_A}{n}-p \right\vert \geq \varepsilon \}=1
$$

在大量独立重复试验下：统计频率 $\overset{P}{\rightarrow}$ 概率  
不好出题故略
### 辛钦大数定律
**定理** 设$X_1,X_2,\cdots,X_n$**独立**且**同分布**，且$\exists E(X_i)=\mu$,则
$$
\lim_{n\rightarrow \infty}P\{ \left\vert \frac{1}{n}\sum_{i=1}^{n}X_i-\mu \right\vert \leq \varepsilon  \}=1\\
or \frac{1}{n}\sum_{i=1}^{n}X_i\overset{P}{\rightarrow }\mu
$$

看似结论是切比雪夫大数定律的特例，但约束条件不同，这个约束条件更强
## 中心*centeral*极限定理
中心只不过是个修饰词
独立同分布independently identically distributed
$\overset{iid}{\sim}$

描述的是在独立同分布的随机变量序列{X}元素足够多的情况下，其和构成的新的随机变量$Y=X_1+X_2+\cdots+X_n$的分布近似与正态分布
### (独立同分布)
**定理** 
$$
\lim_{n\rightarrow \infty}P\left\{ \frac{\sum_{i=1}^{n}X_i-n\mu}{\sqrt{n}\sigma} \leq x \right\}=\Phi(x)
$$
也就是
$$
\because Xi\overset{iid}{\sim}F\\
E(F)=\mu;D(F)=\sigma^{2}\\
\therefore E(\sum_{i=1}^{n}X_i)=n\mu;D(\sum_{i=1}^{n}X_i)=n\sigma^{2}\\
\sum_{i=1}^{n}X_i\sim N(n\mu,n\sigma^{2})\\

\overline{X}\sim N(\mu,\sigma^{2}/n)
$$
### 拉普拉斯
若
$$
X_i\overset{iid}{\sim}B(1,p)
$$
则
$$
\sum_{i=1}^{n}X_i\sim N(np,np(1-p))\\
$$