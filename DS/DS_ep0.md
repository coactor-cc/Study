# ~~绪论~~
## 基本概念和术语
### 数据
客观事物的符号表示，计算机科学中指所有能输入到计算机中的并能被计算机程序处理的符号总称
### 数据元素data element
数据的基本单位
数据项data item 不可分割的最小意义单位
### 数据对象data object
性质相同的**数据元素**的*集合*
### 数据结构data structure
#### 逻辑结构
数据元素+关系

Data Structure=(D,S)  
D为数据元素的有限集  
S为D上关系的有限集  

关系：线性（1对1）、树（1对多）、图（多对多）
#### 物理结构（数据结构在计算机中的物理`实现`）
如何在计算机中表示出逻辑关系
元素element、节点node
- 顺序
- 链式
- 索引
- 散列
#### 操作
在逻辑结构上的操作
### 数据类型（高级语言）
一个值的**集合**，和该集合上的**操作**的总称
原子：整数
结构：数组
### 抽象数据类型（数学抽象特性）
数学模型+操作
抽象数据类型体现了程序设计中问题分解、抽象和信息隐藏的特性
## 算法
>程序=数据结构+算法
对特定问题的求解步骤，指令的有限序列
### 特性(考点)
- 有穷性 停机
- 确定性 无二义性 compared 随机化算法
- 可行性 
- 输入 0-n
- 输出 1-n
### 要求
- 正确性correctness
- 可读性readability
- 健壮性（鲁棒性）robustness
- 效率和低存储量
### 效率的度量
#### ~~$\Omicron()$~~
$\Omicron$ 的形式定义：若f（n）为正整数n的一个函数，则
$$
x_n=\Omicron(f(n))
$$
表示$\exist M>0$，使得当$n\geq n_0$时，有
$$
|x_n|\leq M|f(n)|
$$
#### 时间复杂度（渐进时间复杂度，默认最坏）
##### ~~最好时间复杂度~~
##### 最坏时间复杂度
##### 平均时间复杂度
#### 空间复杂度（默认最坏）
##### 原地工作
额外空间相对于输入数据量来说`是常数`
##### 辅助存储(暂存)
##### 函数递归


