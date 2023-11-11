# 统计学
如何对所得的数据资料进行分析研究，从而对所研究的对象的性质特点作出推断

概率论，研究`已知`随机变量X的  
数理统计：通过对`未知`随机变量X的观察，推断其分布
## 总体与样本
### 总体
总体：试验全部可能的观察值  
个体：每一个可能的观察值  
总体的容量：个体数  

一个总体对应于一个随机变量X的值域，`个体→数一一映射`，故研究未知随机变量X来研究总体
### 样本
简单随机样本：独立且均服从总体分布的随机变量序列{Xi}
$$
X_1,X_2,\cdots,X_n
$$
也可将样本看成一个随机向量`n维随机变量`，记作
$$
(X_1,X_2,\cdots,X_n)
$$

样本值：样本的观测值——一组实数
$$
x_1,x_2,\cdots,x_n
$$

**定义** 对于随机变量$X$，具有未知分布函数$F$，若$X_1,X_2,\cdots,X_n\overset{iid}{\sim}X$,则称其为从。。的容量为n的简单随机样本，则
$$
F^{*}(x_1,x_2,\cdots,x_n)=\prod_{i=1}^{n}F(x_i)
$$
## 样本`函数`的分布

### 统计量与观察值
统计量：n维随机变量函数-样本函数-本质还是个n维随机变量
$$
=g(X_1,X_2,\cdots,X_n)
$$
观察值：将样本值代入得到的函数值
$$
g(x_1,x_2,\cdots,x_n)
$$
### 常用统计量
#### 样本均值
$$
\overline{X}=\frac{1}{n}\sum_{i=1}^{n}X_i=\frac{1}{n}(X_1+X_2+\cdots+X_n)
$$
当$n\rightarrow \infty$时,满足$X_i\overset{iid}{\sim}X$，若$X$具有$\mathbb{E}(X)=\mu$，则依据大数定律
$$
\overline{X}\overset{P}{\rightarrow }\mu
$$
故当这个统计量维度足够大(抽样足够多)时，这个统计量可以用来近似$\mathbb{E}(X)|\mu$

#### 样本方差
用于近似随机变量$X$方差的统计量
$$
S^{2}=\frac{1}{n-1}\sum_{i=1}^{n}(X_i-\overline{X})^{2}
$$
> 注意减的是$\overline{X}$,是无偏的

**证** 计算无偏性，至少你的期望得为$\sigma^{2}$
$$
\begin{aligned}
\because S^{2}&=\frac{1}{n-1}\sum_{i=1}^{n}(X_i^{2}+(\overline{X})^{2}-2X_i\overline{X})\\
&=\frac{1}{n-1}(\sum_{i=1}^{n}X_i^{2}+n(\overline{X})^{2}-2n(\overline{X})^{2})\\
&=\frac{1}{n-1}(\sum_{i=1}^{n}X_i^{2}-n(\overline{X})^{2})\\
\therefore \mathbb{E}(S^{2})&=\frac{1}{n-1}[\sum_{i=1}^{n}\mathbb{E}(X_i^{2})-n\mathbb{E}(\overline{X}^{2})]\\
&=\frac{1}{n-1}[n(\mathbb{E}(X)^{2}+D(X))-n(\mathbb{E}(\overline{X})^{2}+D(\overline{X}))]\\
&=\frac{1}{n-1}[n(\mu^{2}+\sigma^{2})-n(\mu^{2}+\frac{\sigma^{2}}{n})]\\
&=\sigma^{2}\\
\end{aligned}
$$
有效性
$$
D(S^{2})\overset{n=\infty}{\rightarrow}0
$$
故用$S^{2}$来近似$\sigma^{2}$
### 统计量$\chi^{2}$
若$X_i\overset{iid}{\sim}N(0,1)$，则
$$
\chi^{2}=X_1^{2}+X_2^{2}+\cdots+X_n^{2}
$$
服从$\chi^{2}(n)$分布，记为$\chi^{2}\sim\chi^{2}(n)$

#### 性质
1 可加性  

$$
\chi^{2}_a\sim\chi^{2}(n_1),\chi^{2}_b\sim\chi^{2}(n_2)\\
\chi^{2}_a+\chi^{2}_b\sim\chi^{2}(n_1+n_2)

$$
2 数学期望和方差(**背**)
$$
E(\chi^{2}(n))=n;D(\chi^{2}(n))=2n
$$
#### 上$\alpha$分位点
$$
P\{ X> \chi^{2}_\alpha(n) \}=\alpha
$$
### 统计量t
若$X\sim N(0,1),Y\sim\chi^{2}(n)$，且`X，Y相互独立`则
$$
t=\frac{X}{\sqrt{Y/n}}
$$
服从自由的为n的t分布
$$
t\sim t(n)
$$

>应用：正态总统下： $\overline{X}$与$S^{2}$相互独立，而$\overline{X}$与$\sum_{i=1}^{n}{(X_i-\mu)^{2}}$不独立
#### 上$\alpha$分位点
由于图像具有对称性
$$
t_{1-\alpha}(n)=-t_\alpha(n)
$$
#### 性质
$$
E(t(n))=0
$$
### 统计量$F$
若$U\sim\chi^{2}(n_1),V\sim\chi^{2}(n_2)$,且`U，V相互独立`,则统计量
$$
F=\frac{U/n_1}{V/n_2}
$$
服从自由度$(n_1,n_2)$的$F$分布
$$
F\sim F(n_1,n_2)
$$
#### 上$\alpha$分位点
$$
F_{1-\alpha}(n_1,n_2)=\frac{1}{F_\alpha(n_2,n_1)}
$$

#### 
$$
t(n)^{2}\sim F(1,n)
$$

### 正态总体下的常用结论
若总体$X\sim N(\mu,\sigma^{2})$，则有$\mathbb{E}(X)=\mu,D(X)=\sigma^{2}$，则  
1
$$
\overline{X}\sim N(\mu,\frac{\sigma^{2}}{n})
$$
2 
$$
\frac{(n-1)S^{2}}{\sigma^{2}}\sim\chi^{2}(n-1)
$$
3
$$
\frac{\overline{X}-\mu}{S/\sqrt{n}}\sim t(n-1)
$$
4
$$
\frac{{\overline{X}-\mu}^{2}}{S/n}\sim F(1，n-1)
$$
## 参数的估计
猜测模型的参数
### 点估计
#### 矩估计
用$\overline{X}=\mu$反解参数
#### 最大似然估计
计算似然函数最大值
### 正态总体区间估计
$$
X\sim N(\mu,\sigma^{2})
$$
我们推断出一个随机变量它是正态分布，那么我们来用统计量来估计正态分布的两个参数的范围
#### $\mu$的置信区间
统计量的
### 假设检验

#### 两类错误
第一类错误，弃真
第二类错误，取伪
