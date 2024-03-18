# 素数
## 试÷法
$\Omicron(\sqrt{n})$
```c++
inline bool is_prime(int x){
    if(x < 2)
        return false;
    for(register int i = 2; i * i <= x; ++ i)
        if(x % i == 0)
            return false;
    return true;
}
```
## 费马小定理验证法
略，网安||密码学可看

# 因子
## 【前置】如何寻找一个数所有的因子
```c++
#include<vector>
vector<int> get_factor(int n){
    vector<int>factor;
     for(int i = 1; i * i <= n; ++ i){
        if(n % i == 0){
            factor.push_back(i);
            if(i != n / i)
                factor.push_back(n / i);
        }
    }
    return factor;
}
```

## 完全数【2018_1】
如果一个数恰好等于它的真因子之和，则称该数为“完全数    
输出1000以内的完数 格式是：完数=因⼦1+因⼦2+……因⼦n ⽐如说 6=1+2+3;
```c++ 
#include<iostream>
using namespace std;
//bug 最后一个+懒得处理了，烦
int main(){s
     //普素思想，遍历1-1000
    for (int i = 1; i <= 1000; i++) {
        // 找一个数所有的因子,存放在一个int 数组中vector更好？？
        vector<int>factor = get_factor(i);
        // 真因子相加是否等于原数
        int temp = 0;
        for (int j = 0; j < factor.size(); ++j) {
            temp += factor[j];
        }
        if (temp == 2 * i) {//是完数,将自身也加上
            cout << i << "=";
            for (int j = 0; j < factor.size(); ++j)
                if (factor[j] != i)
                    cout << factor[j] << "+";
            cout << endl;
        }
    }
}
```
# 