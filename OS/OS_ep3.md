# 内存管理
## 内存管理基础
### 引入
对于OS来说，内存的组织和实现是的，只需要关心内存所提供的物理地址空间就行

内存管理的核心需求：

1. 内存空间分配与回收
2. 内存空间扩展
3. 地址转换
4. 存储保护



linux  mem_map 空闲分区页map 
swap交换，

页表`给PCB`

多级页表
页表太大的问题
实际使用根本用不到这么多表项
能不能把不使用的页表从逻辑中去掉
去掉的话就不能缺省页号了，因为它不在默认有序  
`不可行，会丧失随机访问的性质`卧槽log级访存

页表寄存器PTBR-IA32叫做CR3

MMU拿到CR3 <<12位

实现虚拟内存的手段
缺页请求中断→缺页中断处理程序
内存换出，也在换入程序里，
```python
do_no_page():
get_free_page():
    if availble :
        get_empty()
    else :
        schudule_page()
```




### 程序的加载|装入(load)
**程序装入内存才能执行**  
#### 静态加载
一次性装入程序的所有部分
#### 动态加载
一个进程所有子程序都以可重定位的形式保存在磁盘上，调用时加载

异常、出错处理的代码
动态加载不需要操作系统提供特别的支持
### 程序的链接
- 静态链接（装入前链接）
- 装入|加载时动态链接（边装入边链接）
- 运行时动态链接（装入后执行链接）

常用于库系统

动态链接通常需要操作系统的帮助

### 地址重定位
PART1 **你也不想之间写代码写32位的地址吧？**  
程序既然不能从0物理地址开始放，就需要一个**重定位**的过程  
#### 逻辑地址
程序的编址B和编址空间4T
#### 物理地址
主存的编址B和编址空间32/64-机器字长绝定
#### 重定位
编译时重定位，特别硬核的系统，静态固化部分功能  
载入时重定位，进程载入后也会移动，  
运行时重定位，内存里也不改,依靠CPU的MMU+操作系统

### 内存保护
使进程只能访问自己的内存空间，  
法1：设置一对上下限寄存器  
法2：重定位寄存器（基址寄存器）+界地址寄存器（限长寄存器）  
TODO 见分段  
## 连续分配管理方式（分区）
系统为用户进程分配的必须是一个连续的存储空间

**这种连续分区管理实际是不使用的，只在虚拟内存中体现**  
### ~~单一连续分配~~
分系统区和用户区，单道用户程序
### 固定分区分配`按图索骥`
将用户区划分为若干固定大小的分区  
数据结构：分区说明表
#### **内部碎片**
分配给某些进程的内存区域中，有些部分没有用上

### 动态分区分配`量体裁衣`
数据结构：空闲分区表  
分配算法  
1. 首次适应
2. 最佳适应
3. 最差适应

首次适应和最佳适应在时间和空间方面都好于最差适应，在空间利用方面难分伯仲，但是首次适应算法更快
首次适应和最佳适应都有外部碎片问题  
#### 外部碎片
内存中的某些空闲分区由于太小而难以利用

50%规则：首次适应算法统计说明，不论采取什么样的优化，设N为可分配块，总有0.5N的外部碎片，即1/3的内存可能不被使用
### 实现
空闲链
空闲分区表
空闲链 双向链表  
**回收时需要合并相邻空闲分区**
##### 紧凑（紧缩，compaction）
紧缩只能在运行重定位模式下可用
## 非连续分配管理方式（分页）
### 分页存储管理
`分页时其实依据创造出了一个和主存一一对应的虚拟页空间，只不过这两个空间大小相等`
#### 概念
##### 页框/帧/主存-辅存层次的块/物理块 page frame
主存空间划分成的若干大小相等的区域通常为4KB

`这是内存分配时的特殊编址方式，而非程序访问时的编址方式——自我解释`
##### 页/页面
进程的逻辑地址空间按页编址（扯淡）只是按页编写页号 逻辑地址=页号+页内偏移量 物理地址=块号+块内偏移量 

`程序的逻辑地址空间（任国林）由于程序需要装入主存才可以执行，（主存通常按字节编址），故程序的存储单元长度必须和主存相同，即采用字节编写逻辑地址`

`而程序通常分段，故用段号+段内地址，附以程序头（各段的在程序中的相对位置和段长）——以文件形式存放`
##### 页表PT
PCB还放页表基址
-存放在PCB中-  

`页号不占存储空间，页表项占整数个字节B`  
*页表项是顺序存储的且主存按B编址*  

页表长度：根据装入策略分配  
##### 页表项(PTE):
控制信息[装入位-缺页,访问位-置换,修改位dirty-写回法,读写位-内存保护]+[Page frame物理页号]`参见任书`

页表项长度——最小长度，实际长度`可能会使一个页框能存放整数个页表项——凑整`


#### 地址变换实现
##### 基本分页地址变换机构
页表寄存器PTR页表起始地址F，页表长度M——由PCB获得
>PCB放在系统区  
两次访存操作
##### 具有块表的地址变换机构
快表（联想寄存器）TLB 页表缓存
最后一步是拼接

TODO 绘图  
#### 多级页表
对页表过大问题的解决方案  


将页号进行拆分，外层页表(outer PT)以高位页号为索引查找低位页号->解决连续分配问题  


在装入时装入外层页表（页目录表），在需要时装入内层页表->解决内存空间占用问题←总感觉不对，页表应常驻内存提高访存效率

多级页表时各级页表不能占用超过一个页的大小  


多级页表结构：
TODO xxxx  

访存次数分析：N+1次访存
### 分段存储管理
**分段是必须的，系统架构决定了硬件分段** 
#### ~~Linux的分段~~

软件+硬件实现分段，PCB进行用户程序`LDT`分段 PCB存段基址、段长、保护位rw  运行时这些基址取出来放到段寄存器里DS CS SS

Linux 操作系统的段表GDT 每个进程的段表LDT ，真正的故事是GDT+LDT`给PCB`

linux 不进行程序分段 用四个GDT表项 用户数据 用户代码 内核数据 内核代码 但是线性地址空间都是0-32也就是共享线性地址，靠保护位实现两态跳转 当然数据往低地址放，代码往高地址放 将IA/32架构的物理寄存器掩盖了

以段为单位分配内存，满足用户在编程和使用上的需要  
逻辑地址=段号+段内地址  
#### **段表**
指令：段名+段内地址（助记符）方便程序员进行内存管理  
段表项（逻辑）=段号+段长+基地址（段首地址）
段表项（物理）=段长+基地址  
段表项长度=最大段内地址空间+主存地址空间->取整B
#### 地址变换机构
要对段内地址进行检查是否越界  
最后一步是做偏移
#### 分页、分段对比
1.分页是信息物理单位，为提高内存利用率，分段信息逻辑单位，为满足用户需要
2.页的大小固定，由系统决定，段的大小不固定，根据信息性质划分
3.分页用户地址空间1维（助记符），分段用户地址空间二维（段名+段内地址）
### 信息共享和保护
通常在分段这层实现；原因
TODO   

### 段页式存储管理
逻辑地址=段号+页号+页内地址
#### 数据结构
段表（物理）=页表长度+页表首地址（块号？？）  
由于分页了，所以页表也肯定是从主存块首地址开始存的，偏移量全0不用记录了  
页表（物理）=块号
#### 地址变换机构
## 虚拟内存管理

### 概念
传统存储管理方式的特征
一次性 驻留性
#### 覆盖技术
程序分段，常用段常驻内存->内存固定区，不常用段，调用时装入->内存覆盖区,现在不用了，对系统不透明  
覆盖区有若干个，不可能同时访问的程序段共享一个覆盖区
#### 交换技术swap
内存紧张时，将某些进程换出外存，把外存中具备运行条件的进程换入内存（中级调度）  
暂时换出外存等待的进程状态称为挂起态：- 就绪挂起- 阻塞挂起

1. 换出后放在外存的什么位置
对换区I/O>文件区
1. 什么时候交换
 进程运行缺页率
1. 换出哪些进程
优先换出阻塞进程，替换算法

特征：整体交换|PCB不动
#### 虚拟内存
**定义** 具有**请求调入**和**置换**功能，从逻辑上堆内存容量加以扩充的存储器系统

**特征*  多次性 对换性 虚拟性

用于解决程序大小受主存容量限制的问题，也可以进一步提高程序并发数
### 请求调页
1. 若当前访问信息不在内存，需要将所需信息**请求调入**内存
2. 内存空间不够，负责将用不到的信息**置换**到外存

如何设计实现具有请求调页功能的页表

`问题`：采用请求调页而不是请求调段，原因是什么？**C**  
A请求调页对用户更透明×  
*操作系统实现的对用户都透明*  
B用户程序需要因为请求调段而重写×  
C请求调页粒度更细，能提高内存效率  
D请求调段不工作在内核态×

#### 页面分配策略
基本策略：用户进程可以分配到任何空闲帧  
~~驻留集~~：**请求分页管理**中给进程分配的物理块的集合
##### 最小帧数
取决于指令集，必须有足够的帧完成单条指令操作

##### 分配算法
解决分多少的问题  
平均分配|带权分配`大小|优先级`
##### 置换范围
初始分配给进程的帧满了从何处获得新的帧`怎么选由置换算法决定`  
**全局置换**  
一个进程的页集合不但取决于进程本身，还取决于其他进程   
不能控制本身的缺页率
更容易动态平衡，具有更好的吞吐量
**局部置换**  
进程页只首自身调页影响
相反
#### 页面调入策略
##### 何时调入
预调页（首次调入）+请求调页  
##### 何处调入
`磁盘对换区`，若不足，不会被修改的文件从文件区  UNIX 未运行在文件区，运行换出进入对换区
##### 调入过程
TODO  **背诵**
#### 页面置换`换出`算法
##### 缺页率
访问页面成功S，访问页面失败F，总访问A=S+F
缺页率
$$f=\frac{F}{A}$$
缺页中断处理时间，页面被修改概率$\beta$,处理时间$t_a$,未被修改处理时间$t_b$
$$
t=\beta\times t_a+(1-\beta)\times t_b
$$
##### 最佳置换算法OPT
淘汰以后最长时间不使用，但是程序无法预知，故`无法实现`，只能作为评价算法
##### 先进先出FIFO
选择驻留时间最久的出——queue
Belady异常——物理块增，缺页率不减反增
##### 最近最久未使用LRU
利用过去预测未来的思想  

实现  
1时间戳方案
2栈方案  

对主存-辅存结构开销过大
均需要硬件的支持，而硬件又很少能对此提供支持

##### ~~LRU近似实现~~  
二次机会算法  

将页表项组织成循环队列，或者用页号+访问位组成循环队列。只需要对访问的页表项的访问位置1`通过MMU硬件做`，不需要改动其他页表项

算法不断查找页表项，读入找到第一个访问位为0的

问题：通常进程中，缺页很少发生，意味着大部分时候进入缺页时页表项的访问位都是1，退化成了先进先出

CLOCK算法  
新增一个指针定时清除访问位的1
#### 进程抖动thrashing
**定义** 频繁的页调度行为。  
**判断标准**：如果一个进程在换页上用的时间多余执行时间    
**原因**：进程太多，每个进程帧太少，不满足程序运行要求     
**预防**：采取局部置换|工作集融入处理机调度，L=S准则，选择暂停进程（减少进程数量）
#### 工作集
工作集：进程在**某段时间间隔**内，进程实际访问页面的集合  
$$
w(t,\Delta)
$$
从t时间向前查找$\Delta$个页面
窗口尺寸（划分时间）：