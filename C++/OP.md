# 运算符重载
## 自增自减++ --
实现为成员函数 
```c++
class Widget{
public:
    Widget& operator++(){
        ++value;
        return *this;
    }
    Widget operator++(int){
        Widget old(*this);
        ++*this;//调用前置自增
        return old;
    }
private:
    int value;
};

```