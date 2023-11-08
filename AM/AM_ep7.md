# 微分方程
## 概念
求解函数关系的方程，解微分方程就是`寻找未知函数`  
**定义** 表示未知函数、**未知函数的导数**与自变量之间关系的方程  

常微分方程：未知函数为一元函数  
偏微分方程：未知函数为多元函数  

阶：微分方程中出现的未知函数的`最高阶导数`的阶数  
线性：未知函数y，y'...之前不能组合  只能加减  
齐次：自变量和常数端是否为0；

>注意区分齐次和齐次型

解：使方程称为恒等式的函数  
通解：含有相互独立的任意常数，个数等于阶数
初值条件：用于确定通解常数值的条件  
特解：不含任意常数的解  
TODO 相互独立，线性相关，线性  
## 求解
### 一阶微分
#### 可分离变量
$$
g(y){\rm d}y=f(x){\rm d}x
$$
**解** 直接积分
#### 可化为可分离变量
TODO 到底时什么鸟题啊  
#### `齐次型`方程
$$
P(x,y){\rm d}x+Q(x,y){\rm d}y=0\\
\frac{{\rm d}y}{{\rm d}x}=\varphi \left(\frac{y}{x}\right)
$$
P(x,y),Q(x,y)每一项次数都相等  
**解** 换元，分离变量  
令$u=\frac{y}{x}$,得
$$
y=ux,\frac{{\rm d}y}{{\rm d}x}=u+x\frac{{\rm d}u}{{\rm d}x}\\
u+x\frac{{\rm d}u}{{\rm d}x}=\varphi(u)\\
\frac{{\rm d}u}{\varphi(u)-u}=\frac{{\rm d}x}{x}
$$
#### 一阶`线性`微分方程
标准形式
$$
\frac{{\rm d}y}{{\rm d}x}+P(x)y=Q(x)
$$
若$Q(x)\equiv 0$则称为齐次线性方程，反之，非齐次线性方程
**解** 
$$
y'·1+Py=Q\\
y'\cdot{\rm e}^{\int P{\rm d}x}+y\cdot{\rm e}^{\int P{\rm d}x}\cdot P={\rm e}^{\int P{\rm d}x}·Q\\
({\rm e}^{\int P{\rm d}x}·y)'={\rm e}^{\int P{\rm d}x}·Q\\
{\rm e}^{\int P{\rm d}x}·y=\int_{}^{}{\rm e}^{\int P{\rm d}x}·Q{\rm d}x+C\\
y={\rm e}^{-\int P{\rm d}x}[\int_{}^{}{\rm e}^{\int P{\rm d}x}·Q{\rm d}x+C]
$$
#### 伯努利方程(可化为一阶线性)
$$
\frac{{\rm d}y}{{\rm d}x}+P(x)y=Q(x)y^{n},n\ne 0,1
$$
**解** 
$$
y^{-n}y'+Py^{1-n}=Q\\
\because (y^{1-n})'=(1-n)y^{-n}y'\\
\therefore (y^{1-n})'+(1-n)Py^{1-n}=(1-n)Q\\
$$
### 可降阶的高阶`常`微分方程
#### n阶导型
$$
y^{(n)}=f(x)
$$

#### 不含y型2阶(简单)
$$
y''=f(x,y')
$$
**解** 令y'=p，y''=p'
#### 不含x型2阶
$$
y''=f(y,y')
$$
**解** 消x,令y'=p
$$
y''=\frac{{\rm d}p}{{\rm d}y}\frac{{\rm d}y}{{\rm d}x}=\frac{{\rm d}p}{{\rm d}y}\cdot p
$$
### 高阶线性`常系数`微分方程
#### 解的结构
$$
y''+P(x)y'+Q(x)y=0
$$
**定理1** 如果函数$y_1(x),y_2(x)$是方程的两个解，则
$$
y=C_1y_1(x)+C_2y_2(x)
$$
也是方程的解  
**定理2** 如果函数$y_1(x),y_2(x)$是方程的两个**线性无关的特解**，则
$$
y=C_1y_1(x)+C_2y_2(x)
$$
是方程的通解  
#### 二阶常系数齐次线性方程通解
$$
y''+py'+qy=0
$$
**解** 取$y={\rm e}^{rx}$求特解，$r$称为特征根
$$
{\rm e}^{r}\cdot r^{2}+{\rm e}^{r}\cdot pr+{\rm e}^{r}\cdot q=0\\
r^{2}+pr+q=0\\
r_{1,2}=\frac{-p\pm \sqrt{p^{2}-4q}}{2}\\
\begin{cases}
\Delta>0,r_1=\frac{-p+\sqrt{p^{2}-4q}}{2};r_2=\frac{-p- \sqrt{p^{2}-4q}}{2}\\
\Delta=0,r_1=r_2=-\frac{p}{2}\\
\Delta<0,r_1=\alpha+\beta {\rm i};r_2=\alpha-\beta {\rm i},
\alpha=-\frac{p}{2},\beta=\frac{\sqrt{4q-p^{2}}}{2}\\
\end{cases}\\
\begin{cases}
\Delta>0,y=C_1{\rm e}^{r_1x}+C_2{\rm e}^{r_2x}\\
\Delta=0,y=(C_1+C_2x){\rm e}^{r_1x}\\
\Delta<0,y={\rm e}^{\alpha x}(C_1\cos\beta x+C_2\sin\beta x)\\
\end{cases}
$$
为了找特解简单，利用${\rm e}^{rx}$的优秀求导性质，来求解，也就是寻找一些形如${\rm e}^{rx}$的解，只是这些解的${r}$不同，故叫${r}$为特征
#### n阶常系数齐次线性方程通解
1.写特征方程  
2.求解`因式分解|观察`  
3.根据特征根，写出通解结构
#### 二阶常系数非齐次线性方程特解
$$
y''+py'+qy=f(x)
$$

##### $f(x)={\rm e}^{\lambda x}P_m(x)$

**解** 特解$y^{*}$设为
$$
{\rm e}^{\lambda x}Q(x)x^{k}
$$
Q(x)为P(x)的通式，k为$\lambda=r$的数量
##### $f(x)={\rm e}^{\alpha x}[P_l(x)\cos \beta x+Q_n(x)\sin \beta x]$
**解** 特解$y^{*}$设为
$$
y^{*}={\rm e}^{\alpha x}[F_1(x)\cos \beta x+F_2(x)\sin \beta x]x^k
$$
F(x)为P、Q最高次的通式，k为$\alpha\pm \beta{\rm i}=r$的数量[0,1]
#### 微分算子法
`非常好用`  
齐次方程写出算子多项式
$$
F(D)=D^{2}+pD+q
$$
设非齐次的f(x)
##### I型$f(x)={\rm e}^{\lambda x}$
若代入得0则求导
$$
y^{*}=
\begin{cases}
\frac{1}{F(\lambda)}{\rm e}^{\lambda x}\\
\frac{1}{F'(\lambda)}x{\rm e}^{\lambda x}\\
\frac{1}{F''(\lambda)}x^{2}{\rm e}^{\lambda x}
\end{cases}
$$
##### II型$f(x)=\sin x$
若遇到无$D^{2}$则有理化分母  
##### III型$f(x)=d+ax+bx^{2}+cx^{3}$
利用$\frac{1}{1-D}=D+D^{2}+\cdots$展开
##### IV型$f(x)=e^{x}\sin x$
$D=D+\alpha$化简$F(D)$


#### 欧拉方程
特点二阶变系数
$$
x^{2}y''+pxy'+qy=f(x), (x>0)
$$
**解** 换元 令$x=e^{t}$
$$
\frac{{\rm d}y}{{\rm d}x}=\frac{{\rm d}y}{{\rm d}t}\cdot\frac{{\rm d}t}{{\rm d}x}=\frac{1}{x}\frac{{\rm d}y}{{\rm d}t}\\
\frac{{\rm d}^{2}y}{{\rm d}x^{2}}=-\frac{1}{x^{2}}\frac{{\rm d}y}{{\rm d}t}+\frac{1}{x}\frac{{\rm d}^{2}y}{{\rm d}t^{2}}\cdot \frac{{\rm d}t}{{\rm d}x}=\frac{1}{x^{2}}(\frac{{\rm d}^{2}y}{{\rm d}t^{2}}-\frac{{\rm d}y}{{\rm d}t})
$$
代入原方程得
$$
y''+(p-1)y'+qy=g(t)
$$
解出t然后回代$t=\ln x$

## 应用(建立微分方程)
TODO xxx物理xxx加速度xxx  