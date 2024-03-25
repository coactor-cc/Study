# Note
## 返回对象引用
### dangling reference悬虚引用
返回一个在函数体中声明的变量的引用
```c++

int& func(){
    int i;
    int& j=i;
    return j;
}
```