# 操作系统概述
## 概念、特征、功能、服务
### 概念
操作系统是一直运行在计算机上的程序，其他程序则分为系统程序和应用程序
>windows 捆绑了一系列应用程序到操作系统
### 特征
并发 共享 虚拟 异步
### 功能
1处理机管理2存储器管理3设备管理4文件管理5用户接口
TODO 
### 服务

TODO     
## 发展和分类
### 单道批处理系统IBM 7094
### 多道批处理系统os 360 IBM 1401
多任务切换和调度
### 分时系统 MULTICS
### 实时系统
## 运行环境
由**中断**驱动，没有中断就不需要动作
内存分为用户区和内核区
指令分为特权指令和非特权指令
### 内核态与用户态
为了确保操作系统正常执行，需要psw有一个字表示模式位   
0-内核态  
1-用户态  
中断信号进入内核态
### 异常与中断
见计组
### 系统调用
POSIX-IEEE定义的系统调用标准尊重了Unix
fork()
read()
write()
open()
getmessage()  
#### ~~接口~~
命令行、图形化界面、应用程序
#### ~~命令行与shell~~
命令是一段程序
gcc
```c
//shell
int main(xxx)
{
char cmd[20];
while(1)
{
    scanf("%s",cmd);
    if(!fork())
    {
        exec(cmd);
    }
    else
        wait();
}

}

```
#### 系统调用实现
要使用特殊中断指令int 0x80，故需要使用宏展开成一段汇编代码
利用c语言利用#define 内嵌汇编
fork()→展开成汇编int 0x80 +调用号，
硬件通过中断机构，调用中断处理程序，系统中断处理程序进入内核进行处理
#### 类型
进程控制fork exec exit  
文件管理read write open close？
设备管理
信息维护
通信
## 结构
### 分层
优点：构造和调试简单化、便于扩充和维护
困难：难定义、调用效率低
### 大内核
性能高
难维护，可靠性不高
### 微内核
可靠
性能
### 模块化
逻辑清晰、易于维护、便于开放
支持动态加载
功能调用效率高 
难以调试 
### 外核
给用户进程分配未经抽象的资源
降低系统一致性
## 操作系统的启动
硬件提供了bios和指令集
bios→bootset`1个扇区`→setup`4个扇区` |实模式汇编→system{head.h-设置gdt。idt(中断向量表)|保护模式汇编，main.c[mem_init();...各种初始化]} 
```c
void mem_init(long start_mem,long end_mem)
{
    int i;
    for(i=0;i<Paging_Pages;i++)
        men_map[i]=USED;
    i=MAP_NR(start_men);
    end_mem-=start_mem;
    emd_mem>>=12;
    while(end_mem --> 0)
        mem_map[i++]=0；
}

```
## `虚拟机`
