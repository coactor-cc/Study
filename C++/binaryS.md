# 二分查找
## 区间[left,right]
给数组nums ,target,要求返回target的index，不存在则返回-1；
```c++
#include<iostream>

template<class T>
int search(T* arr,int start,int end,T key){// 左闭右闭
    //递归中止
    if(start>end)
            return -1;

    int mid=(start+end)/2;
    if(k= =arr[mid])
        return mid;

    if(k>arr[mid])
       return search(arr,mid+1,end,key);
    else
       return search(arr,start,mid-1,key);

}
```

## 区间[left,right)