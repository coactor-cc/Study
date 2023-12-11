# 数组
## 最小>s区间[滑动窗口简介]
滑动窗口法，也叫尺取法，可以用来解决一些查找满足一定条件的连续区间的性质（长度等）的问题。由于区间连续，因此当区间发生变化时，可以通过旧有的计算结果对搜索空间进行剪枝，这样便减少了重复计算，降低了时间复杂度。往往类似于“请找到满足xx的最x的区间（子串、子数组）的xx”这类问题都可以使用该方法进行解决

```python
给定一个含有 n 个正整数的数组和一个正整数 s ，找出该数组中满足其和 ≥ s 的长度最小的连续子数组。如果不存在符合条件的连续子数组，返回 0。
输入: s = 7, nums = [2,3,1,2,4,3]
输出: 2
```

```c++
void solution(int *arg,int length,int s){
    int min=0,sum=0,left=0,right=0;
    while(right<length){
        sum+=arg[++right];
        while(sum<s)
            sum+=arg[++right];
        while(sum>s)
            sum-=arg[left--];
        if(right-left+1<min)
            min=right-left;
    }
    cout<<min<<endl;
}
```
## 所有sum=k的区间(935 2018 ) 
```python
找出整数序列A中所有和等于给定数k的连续子序列
输入：A={5,7,3,3,9,14,4,11,5,5,4,14,14,8} k=25
输出：1,5;7,10;8,11
```
```c++
//算法思想：利用一对指针维护一个滑动窗口，一次扩张和收缩作为一轮
void solution(int A[], int k,int length) {
	int sum = A[0], left = 0, right = 0;
	
	while (right < 14) { //窗口右边界未越界
		sum += A[++right];
		while (sum < k)
			sum += A[++right];// 向右扩张
		while (sum > k)
			sum -= A[left++];// 向右收缩
		if (sum == k)      // 满足条件则输出
			cout << left << "," << right <<endl;
	}
}
```
## 未出现最小k(935 2023,408 2018)
```python
给定一个含n个数的整数数组，找出数组中未出现的最小正整数  
输入：{-5,3,2,3}，{1,2,3}
输出：1,4
```
```c++
void MinInt(int A[],int n){
    bool flag[n];
    for(int i=0;i<n:i++)//标记数组初始化
        flag[i]=false;
    for(int i=0;i<n:i++){//遍历A数组元素
        if(A[i]>0&&flag[A[i]]==false)
            flag[A[i]]=true;
    }
    for(int i=0;i<n;i++)
        if(flag[i]==false){
            std::cout<<i;
            break;
        }
}
```
此题过于简单，没声明难点
# 串
## KMP匹配
思路：剪枝   
利用：当字串在第k位和主串不匹配时，主串前k-1位一定与字串保持一致

step 1:分析字串
case:k=n,n-1...1  
step 2:进行匹配

```c++
int Index_KMP(String S,String T,int next[]){
    int i=1,j=1;
    while(i<=S.length&&j<=T.length){
        if(j==0||S.ch[i]==T.ch[i]){
            ++i;
            ++j;
        }
        else
            j=next[j];
    }
    if(j>T.length)
        return i-T.length;
    else 
        return 0;

}
```
## 最长回文字
2中心回文扩展法 枚举length=1、2的回文并扩展
Manacher算法，记录回文扩展臂长  
3偶数回文插入字符  
4倒序取交集法

# 树
## 二叉搜索树判断(408 2022)
```python
二叉搜索时采用顺序存储(完全二叉树)，
typedef struct{
    int SqBiTNode[MAX_SIZE];
    int ElemNum;
}SqBiTree;
输出：true/false
```
按中序遍历二叉排序树，并维护一个max-遍历中已访问的节点的最大值，由于中心二叉排序树必为升序，故当前节点值若小于max，则不是二叉排序树。
```c++
bool IsBST(SqBiTree &T){
    int node[]=T.SqBiTNode;
    int n=T.ElemNum,max=0;
    bool flag=true;
    Inorder(node[],n,0,flag,max);
    return flag;
}

void Inorder(int node[],int n,int i,bool &flag,int &max){
    if(node[i]!=-1){// 当访问节点存在
        Inorder(node[],n,2*i+1,flag,max);//遍历左子树
        if(node[i]<max)
            flag=false;
        max=node[i];
        Inorder(node[],n,2*i+2,flag,max);//遍历右子树
    }
}
```
时间复杂度$\Omicron(n)$
空间时间复杂度$\Omicron(log_2n)$

反值迭代法
```c++
bool Inorder(SqBiTree &T,int k,int *val){

    if(k<T.ElemNum&&T.SqBiTree[k]!=-1){
        //若访问未越界且节点存在
            if(!Inorder(T,2*k+1,*val))
            //返回递归左子树的判断结果
                return false;
            if(T.SqBiTree[k]<= *val)
            //若当前值未按增序排列,以1为例
                return false;
            //维护val使其最大
            *val=T.SqBiTree[k];
            if(!Inorder(T,2*(k+1),*val))
            //若右子树不合规，传递false
                return false;
    }
    return ture;
}
```
## 二叉搜索树搜索序列


## 二叉树的最大深度（leetcode 104）

递归思想：如果是叶子节点树深度为1，分支节点深度为作用子树最大深度+1
```C++
int maxdepth(Node *T){
    if(T==null) return 0;
    return max(maxdepth(T->lchild),maxdepth(T->rchild))+1;
}
```
## 二叉树不平衡节点个数(935 2017)
```c++
int count=0;
int depth(Node *T):

    if(T==null)
        return 0;
        if(abs(l-r)>1):
            count++;
        return max(depth(T->left),depth(T->right))+1;
}
```
## 最小深度
给定一个二叉树，找出其最小深度。 最小深度是从根节点到最近叶子节点的最短路径上的节点数量。


## 完全二叉树节点个数
```c++
    void countNodes(TreeNode* root){
        if(!root) return 0;
        return countNodes(root->left) + countNodes(root->right) + 1;
    }
```

## 二叉树中序遍历(leetcode 94)
```c++
void inorder(TreeNode* root, vector<int>& res) {
        if (!root) {
            return;
        }
        inorder(root->left, res);
        res.push_back(root->val);
        inorder(root->right, res);
    }
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> res;
        inorder(root, res);
        return res;
    }
```

## 后续遍历二叉树及节点层次
```c++
void postorder(TreeNode* root,int level=1) {
        if (!root)  return 0;
        postorder(root->left,level+1);
        postorder(root->right,level+1);
        cout<<root->data<<level<<endl;
    }
```

# 图

## 有向图 邻接矩阵 最小连通图(935 2022 )
1.BFS 
2.DFS
```python
求有向图的最小连通图，表示形式是伴随矩阵，并且要求输出最小连通n图的边
输入：G 
输出：<v1,v2>...
```
采用了BFS的思想，从初始顶点v开始查找存在的边，若有以v为起点的边存在，则输出该边，并将边的终点i加入队列q，并将visit[i]置为ture，当完成对v节点边的遍历后，从队列q中弹出一个顶点重复该操作，直到队列为空。
```c++
# include<iostream.h>
# include<queue>
#define MAXVALUE 10000
tamplete<class V,class E>

// 注意G用二维数组存 
void CreatTree(Graph<V,E> &G,int v,int n){
      //G为图的矩阵，v为顶点编号 ，n为顶点数量
    bool visit[n];
    queue<int>q;
    for(int i=0;i<n;i++)// 初始化
        visit[i]=0;
        //按起始节点进行广度优先
        CTree(G,v,n);
        while(!q.empty())
            CTree(G;q.pop();n);

}
void CTree(Graph<V,E> &G,int v,int n){
      for(int i=0;i<n;i++){
        if(G[v][i]!=MAXVALUE&&G[v][i]!=0&&visit[i]==0){//边存在且未被访问
            visit[i]=1;
            q.push(i);
            std::cout<<'<'<<v<<','<<i<<'>';
        }
    }
}
```
## 无向图，邻接矩阵 EL路径
```c++
Typedef struct{
    int numVertices,numEdges;
    Char VerticesList[MAXV];
    Int Edge[MAXV][MAXV];
}MGraph;
当G中度为数的顶点个数≤2且为偶数时，存在EL路径，请设计算法判断图是否存在EL路径。
输入：G
输出：true|false
```
```c++
int IsExistEL(MGraph G){
    int n=G.numVertices;
    int degree[n],count=0;

    for(int i=0;i<n;i++)//初始化
        degree[i]=0;
    for(int v=0;v<n];v++) //遍历边表，节点度
        for(int e=0;en<n;e++)
            if(G.Edge[v][e])
                degree[v]++;
    for(int i=0;i<n;i++)//遍历degree，奇数v
        if(degree[i]mod 2==1)
            count++;
    if(count==2&&count==0)//条件判断
        return 1;
    return 0;
}
```




