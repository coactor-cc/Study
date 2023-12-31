函数定义域问题：
$$
\frac{1}{x} \sqrt{x}\ln x \arcsin x
$$

极限的等价
$$
\lim_{x\rightarrow 0}(1+x)^{\frac{1}{x}}-e\sim -\frac{1}{2}ex\\
\lim_{x\rightarrow 0}\ln (x+\sqrt{1+x^{2}}) \sim x
$$


求斜渐进性的b：
$$\lim_{x\rightarrow \infty}[f(x)-kx]=b$$

单根(a)
极值点(b)：偶重根 
拐点(c)：奇重根(非1)  
极值点个数：1a+2b+1c-1  
拐点个数：1a+2b+3c-2  

曲率与曲率半径：
$$
k=\frac{\left\vert y'' \right\vert }{[1+(y')^{2}]^{\frac{2}{3}}}=\frac{1}{R}
$$


弧微分
$$
{\rm d}s=\sqrt{({\rm d}x)^{2}+({\rm d}y)^{2}}\\
=
\begin{cases}
\sqrt{1+y'^{2}}{\rm d}x   , y\rightarrow x\\ 
\sqrt{\varphi^{2}(t)+\psi^{2}(t)}{\rm d}t ,x,y\rightarrow t\\
\sqrt{r^{2}+r'^{2}(\theta)}{\rm d}\theta,r\rightarrow \theta
\end{cases}
$$


积分公式：
$$
\int_{}^{}\sec x{\rm d}x=\int_{}^{}\frac{1}{\cos x}{\rm d}x=\\
\int_{}^{}\csc x{\rm d}x=\int_{}^{}\frac{1}{\sin x}{\rm d}x=\\
\int_{}^{}\sec^{2} x{\rm d}x=\int_{}^{}\frac{1}{\cos^{2} x}{\rm d}x=\\
\int_{}^{}\csc^{2} x{\rm d}x=\int_{}^{}\frac{1}{\sin^{2} x}{\rm d}x=\\
$$
积快快公式
$$
\int_{}^{}e^{ax}\cos bx{\rm d}=\\\frac{1}{a^{2}+b^{2}}[(e^{ax})'\cos bx-(\cos bx)'e^{ax}]
$$
华理士公式及其推论



参数方程积面积
$$
\begin{cases}
x=\varphi(t)\\
y=\psi(t)
\end{cases}\\
A=\int_{\varphi^{-1}(a)}^{\varphi^{-1}(b)}\psi(t){\rm d}\varphi(t)
$$
极坐标积面积
$$
A=\int_{\alpha}^{\beta}\frac{1}{2}r^{2}(\theta){\rm d}\theta
$$



欧拉方程
$$
x^{2}y''+pxy'+qy=f(x),(x>0)
$$
$$
y''+(p-1)y'+qy=g(t)
$$
解出t然后`回代`$t=\ln x$


傅里叶级数
$$
a_n=\frac{1}{l}\int_{-l}^{l}f(x)\cos \frac{n\pi}{l}x {\rm d}x\\
b_n=\frac{1}{l}\int_{-l}^{l}f(x)\sin \frac{n\pi}{l}x {\rm d}x\\
f(x)\sim \frac{a_0}{2}+\sum_{i=1}^{n}(a_n\cos \frac{n\pi}{l}x+b_n\sin \frac{n\pi}{l}x)
$$
特殊的，当$l=\pi$时
$$
a_n=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\cos nx {\rm d}x\\
b_n=\frac{1}{\pi}\int_{-\pi}^{\pi}f(x)\sin nx {\rm d}x\\
f(x)\sim \frac{a_0}{2}+\sum_{i=1}^{n}(a_n\cos  nx+b_n\sin  nx)
$$

一型曲线积分的斯托克斯公式  
要求：封闭，空间曲线
$$
\oint_\Gamma P {\rm d}x+Q{\rm d}y+R{\rm d}z=\iint_\Sigma \begin{vmatrix}
    {\rm d}y{\rm d}z & {\rm d}z{\rm d}x & {\rm d}x{\rm d}y \\
    \frac{{\rm d}}{{\rm d}x} & \frac{{\rm d}}{{\rm d}y} & \frac{{\rm d}}{{\rm d}z} \\
    P & Q & R \\
\end{vmatrix}
$$
其中，$\Gamma$与$\Sigma$法向量成右手系