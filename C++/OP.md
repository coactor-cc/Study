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
## 输入输出运算符
```c++
class T{
    int x;
    int y;
public:
    friend ostream& operator<<(ostream &os,const &T t);
};

ostream& operator<<(ostream &os,const &T t){
    os<<t.x<<t.y<<endl;

}
```