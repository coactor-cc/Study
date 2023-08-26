# 向量
**定义** n个有次序的数所组成的数组

几何空间是点集，由于向量的终点可以与点集一一对应，故n维向量空间$\mathbb{R}^{n}$

向量集

向量组：若干同维数的列向量或行向量组成的集合

## 向量组的线性表示
**定义** 线性组合  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,$\forall \lambda_1,\lambda_2,\cdots,\lambda_n$,表达式
$$
k_1a_1+k_2a_2+\cdots+k_na_n
$$
称为A的一个线性组合  

**定义** 线性表示  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,$\exists\lambda_1,\lambda_2,\cdots,\lambda_n$使得
$$
b=k_1a_1+k_2a_2+\cdots+k_na_n
$$
则b是向量组A的线性组合，b能用A线性表示

**定理1** 向量b能用向量组线性表示$\Leftrightarrow$r(A)=r(B[a,a,a,...,b])

## 向量组等价

## 向量组的线性相关与无关
**定义** 线性相关  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,$\exists\lambda_1,\lambda_2,\cdots,\lambda_n$不全为0，使得
$$
k_1a_1+k_2a_2+\cdots+k_na_n=0
$$
则称向量组A线性相关

`至少有一个向量是多余的`  
**定义** 线性无关  
给定向量组$A:a_1,a_2,a_3,\cdots a_n$,当且仅当$\lambda_1=\lambda_2=\cdots=\lambda_n=0$，使得
$$
k_1a_1+k_2a_2+\cdots+k_na_n=0
$$
则称向量组A线性无关

`非线性相关，必无关`

证明紧扣定义
### 判断线性相关7大定理

1 A线性相关$\Leftrightarrow$A中至少有一个$a_i$可由其余n-1个向量线性表示  
**证** 必要性
不妨设$k_i\ne 0$,则
$$
a_i=-(\frac{1}{k_i})(k_1a_1+\cdots+k_{i-1}a_{i-1}+k_{i+1}a_{i+1}+\cdots+k_na_n)
$$

2 若向量组$a_1,a_2,a_3,\cdots a_n$线性无关，$b,a_1,a_2,a_3,\cdots a_n$线性相关，则b能用$a_1,a_2,a_3,\cdots a_n$`唯一线性`表示  
**证** 
TODO 嘻嘻嘻  

