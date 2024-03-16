
# 字符数组处理
不允许使用C++ STL，也就是说string类没法用
能不能用cstring？？
## cstring
### strcpy()
char* strcpy(char* dis,const char* source);
### strncpy()
char* strncpy(char* dis,const char* source,size_t num);
### strcat()
字符串拼接
### strcmp()
返回 =0 相同 
### strtok()
切分字符串 

first use: strtok(str," ,;");
else:strtok(NULL," ,;);
# 随机函数
## cstdlib
```c++
void srand(unsigned int seed);//设置种子
int rand(void);//产生随机整数
```


