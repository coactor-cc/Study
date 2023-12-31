# 喝前摇一摇
二项分布概率最大的取值，
$$
k=\left\lceil (n+1)p \right\rceil 
$$
若(n+1)p为整数继续向下取一位   
几何分布  
无记忆性  
泊松分布
$$
P\{ X=k \}=\frac{\lambda^{k}{\rm e}^{-\lambda}}{k!},k=1,2,\cdots
$$  
泊松定理 $\lambda=np$用泊松估计二项概率

指数分布
$$
f(x)=
\begin{cases}
\begin{aligned}
&\lambda {\rm e}^{-\lambda x},&&x>0,\\
&0,&&其他,
\end{aligned}
\end{cases}
$$

二维正态分布
$$
(X,Y)\sim N(\mu_1,\mu_2,\sigma_1^{2},\sigma_2^{2},\rho)
$$
注意参数顺序和意义

切比雪夫不等式
$$
P\{ \left\vert X-\mu \right\vert \geq \varepsilon  \}\leq \frac{\sigma^{2}}{\varepsilon ^{2}} 
$$

数字特征
$$
E(XY)=E(X)E(Y)+\operatorname{Cov}(X,Y)\\
D(X\pm Y)=D(X)+D(Y)\pm 2\operatorname{Cov}(X,Y)\\
\rho_{XY}=\frac{Cov(X,Y)}{\sqrt{D(X)D(Y)}}
$$


正态总体下，统计量的结论
$$
\overline{X}\sim N(\mu,\frac{\sigma^{2}}{n})\\
\frac{1}{\sigma^{2}}\sum_{i=1}^{n}(X_i-\mu)^{2}\sim \chi^{2} (n)\\
\frac{n-1}{\sigma^{2}}S^{2}=\frac{1}{\sigma^{2}}\sum_{i=1}^{n}(X_i-\overline{X})^{2}\sim \chi^{2} (n-1)\\
$$
$\overline{X}$与$S^{2}$相互独立，故
$$
\frac{\sqrt{n}(\overline{X}-\mu)}{S}\sim t(n-1)\\
\frac{n(\overline{X}-\mu)^{2}}{S}\sim F(1,n-1)
$$
而$\overline{X}$与$\sum_{i=1}^{n}{(X_i-\mu)^{2}}$不独立,故
$$
\frac{\sqrt{n}(\overline{X}-\mu)}{\sqrt{\frac{1}{n}\sum_{i=1}^{n}(X_i-\mu)^{2}}}\nsim t(n)
$$


$\alpha$分位数与$\Phi(x)$,设随机变量$X\sim N(\mu,\sigma^{2})$,则
$$
\Phi(t)=P\{ X \leq t \}\\
P\{ X>t \}=1-\Phi(t)=\Phi(-t)\\
P\{ X>x \}=\alpha\\
X_\alpha=-t

$$




# 【5】古典概型
离散等可能  
## 随机分配问题
## 随机抽样问题


## 数字特征
### 切比雪夫不等式【5'】可能考


## 大数定理和中心极限定理【5'】可能考

# 数理统计
## 统计量的分布【5'】必考 一般选择
