# HashMap
HashMap中根据键值对无序存储数据

## import
```java
import java.util.HashMap;
import java.util.Map;
```

## 新建Map对象
```java
Map<Integer,String> testMap=new HashMap<>();
```

## 添加元素
  使用put方法
  ```java
  HashMap.put(key,value);
  ```
  * 实例：
    ```java
    testMap.put(1,"one");
    testMap.put(2,"two");
    System.out.println(testMap);
    ```
    输出结果如下：
    ```java
    {1=one, 2=two}
    ```
## 访问元素
  使用get方法
  ```java
  value=HashMap.get(key);
  ```
  * 实例：
    ```java
    System.out.println(testMap.get(1));
    System.out.println(testMap.get(2));
    System.out.println(testMap.get(3));
    ```
    输出结果如下：
    ```java
    one
    two
    null//key=3不存在，输出空
    ```
## 删除元素
  使用remove方法
  ```java
  HashMap.remove(key);
  ```
  * 实例：
    ```java
    testMap.remove(1);
    System.out.println(testMap);
    ```
    输出结果如下：
    ```java
    {2=two}
    ```
## 删除所有元素
  使用clear方法
  ```java
  HashMap.clear();
  ```
  * 实例：
    ```java
    testMap.clear();
    System.out.println(testMap);
    ```
    输出结果如下：
    ```java
    {}//空
    ```
## 其他常用方法
* size方法返回元素数量
  ```java
  HashMap.size();
  ```
* keySet方法返回key的集合
  ```java
  for(int i:HashMap.keySet()){//使用for-each语句迭代
    System.out.println("key:"+i+",value:"+test.get(i));
  }
  ```
  输出结果如下：
  ```java
  key:1,value:one
  key:2,value:two
  ```
* values方法返回value集合
  ```java
  for(String value:HashMap.values()){
    System.out.print(value+",");
  }
  ```
  输出结果如下：
  ```java
  one,two,
  ```