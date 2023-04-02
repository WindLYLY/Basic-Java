# for-each语句
## 基本格式
```java
for(elemtype name:数据合集){
    //details
    }
```
数据合集可为List,Set,Array
## 示例
```java
int[]num={1,2,3,4,5,6,7,8,9,10};
for(int n:num){
    System.out.print(n+" ");
}
```
输出如下：\
[![20230402120600.png](https://i.postimg.cc/Pq0GZ9WR/20230402120600.png)](https://postimg.cc/kVNhPjhQ)
## 用法实例
题目：\
[附上力扣589题原链接](https://leetcode.cn/problems/n-ary-tree-preorder-traversal/)\
[![20230402121142.png](https://i.postimg.cc/Kzq5Rkd7/20230402121142.png)](https://postimg.cc/sQWWLXf1)\
题目已定义的Node类n叉树：
```java
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/
```
解法如下：
```java
class Solution {
    public List<Integer> preorder(Node root) {
        List<Integer> res=new ArrayList<Integer>();//定义结果列表
        ad(root,res);//定义递归函数，函数为先序遍历并把val值加到res列表中
        return res;
    }
    public void ad(Node root,List<Integer> res){
        if(root==null)return;
        res.add(root.val);//先序遍历需要先添加值再寻找孩子节点
        for(Node node:root.children){//本文重点，for-each语句使用，遍历孩子节点
            ad(node,res);//递归使用函数，对孩子节点进行先序遍历
        }
    }
}
```
\
\
完结！
