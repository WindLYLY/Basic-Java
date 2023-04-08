# Queue队列
## 队列的创建
头文件：
```java
import java.util.Queue;
import java.util.LinkedList;
//import java.util.*;代替亦可
```
一般用LinkedList实现队列：
```java
Queue<Integer> queue=new LinkedList<>();
```
## 压入元素
即元素入队，且在队尾
* add方法：
    ```java
    queue.add(1);
    queue.add(2);
    ```
* offer方法：
    ```java
    queue.offer(3);
    queue.offer(4);
    ```
这两个方法都有返回值，为压入元素的值\
区别为：\
超出容量时add方法会抛出异常，而offer方法会返回false
## 队列的复制
* addAll方法：
  ```java
  Queue<Integer> clone=new LinkedList<>();
  clone.addAll(queue);//将queue的数据复制到新队列clone中
  ```
## 删除元素
即元素出队，同时删除元素
* remove方法：
    ```java
    int a=queue.remove();
    //返回并删除队头元素，即a=1
    ```
* poll方法：
  ```java
  int b=queue.poll();
  //b=2
  ```
区别为：\
队列容量为0时remove方法抛出异常，而poll返回false
## 获取队头元素
返回队头元素，但不删除/不出队
* element方法
  ```java
  int c=queue.element();
  //c=3
  ```
* peek方法
  ```java
  queue.remove();
  //队头元素3出队，此时队头元素为4
  int d=queue.peek();
  //d=4
  ```
区别为：\
队列容量为0时element方法会抛出异常，peek方法会返回null\
\
\
完结！
