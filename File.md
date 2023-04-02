# File操作
## 输入（读取文件）
使用Scanner类
  ### 示例代码：
  * import\
    import java.io.*代表系统在java.io类内寻找需要的类
    ```java
    import java.io.File;//可以用import java.io.*;代替
    import java.util.Scanner;
    ```
* 创建文件对象
  ```
  File file=new File("D:\\src\\aa.txt");
  ```
* 为文件创建一个Scanner对象\
  在平时，我们为键盘创建Scanner对象的代码如下：
  ```java
  Scanner input=new Scanner(System.in);
  ```
  类似地，我们为文件创建Scanner对象的代码如下：
  ```java
  Scanner input=null;//new可能异常，用try-catch语句处理
  try{input=new Scanner(file);}
  catch(Exception e){System.out.println("Scanner对象创建错误！")}
  ```
* 用String数据类型接受文件的输入\
  假设有十个字符串（Scanner对象会自动以空格为分隔符）
  ```java
  String[]s=new String[10];
  int i=0;
  while(input.hasNext()){
    String s[i]=input.next();
    i++;
  }
  ```
 * 在使用完文件输入后，及时释放对象
    ```java
    input.close();
    ```
* 根据要求对String进行后续处理，不再赘述
## 输出（创建/修改文件）
使用PrintStream类
### 示例代码：
* import 
  ```java
  import java.io.File;
  import java.io.PrintStream;
  //也可以用import java.io.*;代替
  ```
（主函数字段省略）

* 创建文件对象
  ```java
  File file=new File("name.txt");//创建文件对象，文件不存在会自动创建
  ```
* 创建打印输出流
  ```java
  PrintStream ps=null;//new可能异常，用try-catch语句处理
  try{ps=new PrintStream("D:\\scr\\test.txt");}//文件具体路径
  catch(Exception e){System.out.println("输出流创建错误！");}
  ```
* 把创建的打印输出流赋给系统。即系统下次向 ps输出\
在此之前，最好事先保存系统默认的打印输出流
  ```java
  PrintStream out=System.out;//保存系统默认的打印输出流
  System.setOut(ps);//改变打印输出流
  ```
  此时输出都在文件上 
  ```java
  System.out.println("Hello World!");
  System.out.println("你好!");
  ```
  文件如下图:\
\
[![File-1.png](https://i.postimg.cc/FHrxwPYh/File-1.png)](https://postimg.cc/MvLRQm0L)
* 恢复打印输出流
  ```java
  ps.close();//使用完及时释放
  System.setOut(out);
  System.out.Println("输出流回到屏幕");
  ```
  输出如下图\
[![File-2.png](https://i.postimg.cc/9M3yDBd8/File-2.png)](https://postimg.cc/CZNRtk6k)
\
\
\
本记录为使用PrintStream改变系统打印输出流的方法输出内容到文件，本人觉得较为通用和方便，故记录。此外还有许多类都可以实现对文件的修改和创建操作，在此不再赘述\
\
完结！
