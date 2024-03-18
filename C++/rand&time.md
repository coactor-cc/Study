# 随机函数
## cstdlib
```c++
#include<cstdlib>
void srand(unsigned int seed);//设置种子
int rand(void);//产生随机整数
```
# 定时
## ctime
利用time设置随机数
```c++
#include<ctime>
srand(time(0));// 利用time的功能实现随机
```