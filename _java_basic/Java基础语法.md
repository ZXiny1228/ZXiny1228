---
title: "Java基础语法"
date: 2025-01-01
toc: true 
render_with_liquid: false  
---

# Java基础语法



## 1 Java入门

### 1.1 环境变量

<font color=blue>**1. 启动CMD**</font>

按下快捷键 ```win + R```，在运行窗口中输入 ```cmd```

cmd默认操作C盘下的users文件夹下的XXX文件夹（XXX就是计算机名）

<font color=blue>**2. 常用CMD命令**</font>

| 操作               | 说明                              |
| ------------------ | --------------------------------- |
| 盘符名称:          | 盘符切换。E:回车，表示切换到E盘。 |
| dir                | 查看当前路径下的内容。            |
| cd 目录            | 进入单级目录。cd itheima          |
| cd ..              | 回退到上一级目录。                |
| cd 目录1\目录2\... | 进入多级目录。cd itheima\JavaSE   |
| cd \               | 回退到盘符目录。                  |
| cls                | 清屏。                            |
| exit               | 退出命令提示符窗口。              |

<font color=blue>**3. 配置环境变量**</font>

- **作用**：想要在CMD的任意目录下，都可以启动某一个软件，那么就可以把这个软件的路径配置到环境变量中的```PATH```里面。在启动软件的时候，操作系统会先在当前路径下找，如果在当前目录没有再到环境变量的路径中去找。如果都找不到就提示无法启动

- **步骤**：

  - 右键我的电脑，选择属性

  - 点击左侧的高级系统设置，再点击下面的环境变量
  - 找系统变量里面的PATH
  - 把软件的完整路径，配置到PATH当中就可以了
  - （可做可不做）把自己配置的路径，移动到最上面




### 1.2 下载安装Java环境

1. **下载**：通过官方网站获取JDK [http://www.oracle.com](http://www.oracle.com/)
2. **安装**：注意安装路径不可有中文、空格等特殊符号
3. **配置环境变量**：建立JAVA_HOME，将%JAVA_HOME%把配置到PATH当中%JAVA_HOME%\bin
4. **JDK 的安装目录**：

| 目录名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| bin      | 该路径下存放了JDK的各种工具命令。javac和java就放在这个目录。 |
| conf     | 该路径下存放了JDK的相关配置文件。                            |
| include  | 该路径下存放了一些平台特定的头文件。                         |
| jmods    | 该路径下存放了JDK的各种模块。                                |
| legal    | 该路径下存放了JDK各模块的授权文档。                          |
| lib      | 该路径下存放了JDK工具的一些补充JAR包。                       |

<font color=blue>**利用电脑Java环境运行：**</font>

1. **书写代码**：用记事本书写 .java 文件 (程序员自己编写的代码)
2. **编译代码**：编译产生 .class 文件 (交给计算机执行的文件)

3. **运行代码**：运行编译后的 .class 文件

> 在cmd中用到两个命令：
>
> ​	javac + 文件名 + 后缀名 （就是编译java文件）
>
> ​	java + 文件名（运行编译之后的class文件）
>
> ==注意==：编译命令后的java文件名需要带文件后缀.java，运行命令后的class文件不带文件后缀.class



### 1.3 Java的主要特性

<font color=blue>**1. Java的三大平台**</font>

- **JavaSE**：其他两个版本的基础
- **JavaME**：Java语言小型版，用于嵌入式消费类电子设备或小型移动设备(手机)开发，已逐渐被安卓和IOS替代
- **JavaEE**：用于Web方向的网站开发，主要从事后台服务器开发

<font color=blue>**2. Java的主要特性**</font>：<font color=red>**一次编译、处处可用**</font>

- 面向对象
- 安全性
- 多线程
- 简单易用
- 开源
- 跨平台：针对不同的操作系统，Java提供了不同的虚拟机，会将其翻译成操作系统可看懂的语言

<img src="javaBasis_assets\1.png" alt="image-20210923091350952" style="zoom: 50%;" />

<font color=blue>**3. JRE 和 JDK**</font>

<img src="javaBasis_assets\2.png" alt="image-20210923091544110" style="zoom:50%;" />

**JVM**（Java Virtual Machine），Java虚拟机，真正运行Java程序的地方

**JRE**（Java Runtime Environment），Java运行环境，包含了JVM和Java的核心类库（Java API）

**JDK**（Java Development Kit），Java开发工具，包含了JRE和开发工具

总结：**只需安装JDK即可，它包含了java的运行环境和虚拟机**

---



## 2 Java基本概念

### 2.1 数据类型

<font color=blue>**1. Java语言数据类型的分类**</font>

- 基本数据类型
- 引用数据类型

<font color=blue>**2.基本数据类型**</font>

| 数据类型 | 关键字  | 内存占用 |                 取值范围                  |
| :------: | :-----: | :------: | :---------------------------------------: |
|   整数   |  byte   |    1     |    负的2的7次方 ~ 2的7次方-1(-128~127)    |
|          |  short  |    2     | 负的2的15次方 ~ 2的15次方-1(-32768~32767) |
|          |   int   |    4     |        负的2的31次方 ~ 2的31次方-1        |
|          |  long   |    8     |        负的2的63次方 ~ 2的63次方-1        |
|  浮点数  |  float  |    4     |        1.401298e-45 ~ 3.402823e+38        |
|          | double  |    8     |      4.9000000e-324 ~ 1.797693e+308       |
|   字符   |  char   |    2     |                  0-65535                  |
|   布尔   | boolean |    1     |                true，false                |

**说明**：

- e+38表示是乘以10的38次方，同样，e-45表示乘以10的负45次方
- 在java中整数默认是**int**类型，浮点数默认是**double**类型

**==需要记忆==：**

- byte类型的取值范围：-128 ~ 127

- int类型的大概取值范围：-21亿多  ~ 21亿多

- 整数类型和小数类型的取值范围大小关系：double > float > long > int > short > byte

- 最为常用的数据类型选择：

  - 在定义变量的时候，要根据实际的情况来选择不同类型的变量

    比如：人的年龄，可以选择byte类型；地球的年龄，可以选择long类型

  - 如果整数类型中，不太确定范围，那么默认使用**int类型**

  - 如果小数类型中，不太确定范围，那么默认使用**double类型**

  - 如果要定义一个long类型的变量，那么在数据值的后面需要加上**L后缀**（大小写都可以，建议大写）

  - 如果要定义一个float类型的变量，那么在数据值的后面需要加上**F后缀**（大小写都可以）

    **注意：<font color=red>默认int和double，long和float后在定义时需要加后缀</font>**

    

### 2.2 标识符

<font color=blue>**1. 硬性要求**</font>

- 必须由数字、字母、下划线_、美元符号$组成
- 数字不能开头
- 不能是关键字
- 区分大小写

<font color=blue>**2. 软件建议**</font>

- <font color=red>**小驼峰命名法（变量名、方法名)**</font>
  * 如果是一个单词，那么全部小写，比如：name

  * 如果是多个单词，那么从第二个单词开始，首字母大写，比如：firstName、maxAge


- <font color=red>**大驼峰命名法（类名)**</font>

  * 如果是一个单词，那么首字母大写，比如：Demo、Test


  * 如果是多个单词，那么每一个单词首字母都需要大写，比如：HelloWorld


- <font color=red>**阿里巴巴命名规范细节**</font>

  - 尽量不要用拼音。但是一些国际通用的拼音可视为英文单词

    - 正确：alibaba、hangzhou、nanjing
    - 错误：jiage、dazhe

  - 平时在给变量名、方法名、类名起名字的时候，不要使用下划线或美元符号

    - 错误：_name

    - 正确：name

      

### 2.3 键盘录入Scanner

<font color=blue>**1. 使用步骤**</font>

- **导包**:  先找到Scanner这个类在哪
- **创建对象**：申明一下，准备开始用Scanner这个类
- **接收数据**：真正干活的代码

<font color=blue>**2. 代码示例**</font>

```java
//1.导包
import java.util.Scanner;

public class ScannerDemo{
	public static void main(String[] args){
		//2.创建对象
		Scanner sc = new Scanner(System.in);
		//3.接收数据
		//当程序运行之后，在键盘输入的数据就会被变量i给接收了
		System.out.println("请输入一个数字");
		int i = sc.nextInt();
		System.out.println(i);
	}
}
```

<font color=blue>**3. 两套体系**</font>

- 第一套体系

  - **nextInt()**：接收整数

  - **nextDouble()**：接收小数

  - **next()**：接收字符串

    (**遇到空格、制表符、回车，就停止接受**，这些符号后面的数据则不会接受)

- 第二套体系

  - **nextLine()**：接收字符串

<font color=blue>**4. 四个细节**</font>

**① 第一个细节**

next()，nextInt()，nextDouble() 在接收数据的时候，遇到空格，回车，制表符其中一个就会**停止接收数据**

```java
Scanner sc = new Scanner(System.in);
double d = sc.nextDouble(); // 1.1 2.2
System.out.println(d);      // 1.1
//表示nextDouble方法在接收数据的时候，遇到空格就停止了，后面的本次不接收
```

**② 第二个细节**

next()，nextInt()，nextDouble() 在接收数据的时候，会遇到空格，回车，制表符其中一个就会停止接收数据。但是这些符号 + 后面的数据还在内存中并没有接收。**如果后面还有其他键盘录入的方法，会自动将这些数据接收**

```java
Scanner sc = new Scanner(System.in);
String s1 = sc.next();  // a b
String s2 = sc.next();  // ...
System.out.println(s1); // a
System.out.println(s2); // b
//空格+b还在内存中
//第二个next会去掉前面的空格，只接收b
//所以第二个s2打印出来是b
```

**③ 第三个细节**

nextLine（）方法是把**一整行全部接收完毕**

```java
Scanner sc = new Scanner(System.in);
String s = sc.nextLine();  // a b
System.out.println(s);     // a b
//nextLine不会过滤前面和后面的空格，会把这一整行数据全部接收完毕。
```

**④ 混用引起的后果**

<font color=red>**上面说的两套键盘录入不能混用，如果混用会有严重的后果**</font>

```java
Scanner sc = new Scanner(System.in);//①
int i = sc.nextInt();    //123 + 回车
String s = sc.nextLine();//+回车 被nextLine吸收
System.out.println(i);   //123
System.out.println(s);   //nextLine接收不到数据
```

<font color=blue>**5. 如何使用**</font>

- next（）、nextInt（）、nextDouble（）这三个配套使用
  - 如果用了这三个其中一个，就不要用nextLine（）

- nextLine（）单独使用
  - 如果想要整数，那么先接收，再使用Integer.parseInt进行类型转换

```java
Scanner sc = new Scanner(System.in);
String s = sc.next();                 //123
System.out.println("此时为字符串" + s); //此时为字符串123
int i = sc.nextInt();                 //123
System.out.println("此时为整数：" + i); //此时为整数123
```

```java
Scanner sc = new Scanner(System.in);
String s = sc.nextLine();            //123
System.out.println("此时为字符串" + s);//此时为字符串123
int i = Integer.parseInt(s);         //想要整数再进行转换
System.out.println("此时为整数：" + i);
```



### 2.4 运算符

#### 2.4.1 算术运算符

<font color=blue>**1. 分类**</font>：``` + - * % / ```

<font color=blue>**2. 运算特点：**</font>

- 除法 `/`

  - 整数相除结果只能得到整除，如果结果想要**是小数，必须要有小数参数**

  - 小数直接参与运算，得到的结果有可能是**不精确**的

    ```java
    System.out.println( 10 / 3); //3
    System.out.println(10.0 / 3);//3.3333333333333335
    ```

- 取模、取余 `%`

  - **应用场景**：可以利用取模来判断一个数是**奇数还是偶数**

    ```java
    System.out.println(10 % 2);//0
    System.out.println(10 % 3);//1
    
    System.out.println(15 % 2);//1  奇数
    ```

###### 练习：数值拆分

==需求：键盘录入一个三位数，将其拆分为个位、十位、百位后，打印在控制台==

```java
//导包 --- 创建对象 --- 接收数据
Scanner sc = new Scanner(System.in);
System.out.println("请输入一个三位数");
int number = sc.nextInt();

//针对于任意的一个数而言
//个位： 数字 % 10
int ones = number % 10;
//十位： 数字 / 10 % 10
int tens = number / 10 % 10;
//百位： 数字 / 100 % 10
int hundreds = number / 100  % 10;

System.out.println(ones);
System.out.println(tens);
System.out.println(hundreds);
```

#### 2.4.2 类型转换

<font color=blue>**1. 隐式转换**</font>

- **概念**：<font color=red>**自动类型提升**</font>，将一个取值范围小的数据或变量，赋值给另一个取值范围大的变量，程序自动帮助完成

- **规则**：<font color=red>**小的给大的，直接给**</font>

  - 取值范围小的和取值范围大的进行运算，小的会先提升为大的，再进行运算

  - ```byte、short、char```三种类型的数据在运算时，都会先提升为```int```，再进行运算

- **取值范围从小到大的关系**：```byte short int long float double```

###### 练习：隐式转换

==请看下面案例是否有误，如果有问题，请说出原因，如果没有问题，请说出运算过程和运算结果==

```java
double d = 10;
System.out.println(d);
```

​	结果：10.0

​	解释：10是整数，整数默认是int类型的。在赋值的时候把一个小的赋值给一个大的是可以直接给的

```java
byte b1 = 10;
byte b2 = 20;
result = b1 + b2;
问变量result是什么类型的？
```

​	结果：int

​	解释：b1和b2都是byte类型, 在参与计算的时候，变量的值都会自动提升为int类型的。最终其实就是两个int类型的相加，最终结果也是int类型的

<font color=blue>**2. 强制转换**</font>

- **概念**：如果要把一个取值范围大的数据或者变量赋值给另一个取值范围小的变量。是不允许直接操作。需要加入强制转换

- **书写格式**：<font color=red>**目标数据类型  变量名 = (目标数据类型) 被强转的数据**</font>

```java
public class Demo {
    public static void main(String[] args) {
        double a = 12.3;
        int b = (int) a;
        System.out.println(b);//12
    }
}
```

- ==**注意**==：强制转换有可能会导致数据发生错误（**数据的精度丢失**）

#### 2.4.3 字符串的 + 操作

<font color=blue>**1. 核心技巧**</font>

* 当 + 操作中**出现**字符串时，此时就是**字符串**的连接符，会将前后的数据进行拼接，并产生一个新的字符串

* 当连续进行+操作时，从左到右逐个执行的

```java
1 + 2 + "abc" + 2 + 1
```

结果：“3abc21”

<font color=blue>**2. 字符的 + 操作**</font>

当 + 操作中出现了字符，会拿着字符到计算机内置的```ASCII码表```中去查对应的数字，然后再进行计算

```java
char c = 'a';
int result = c + 0;
System.out.println(result);//97
```

ASCII码表中：<font color=red>**'a'   -----    97      'A'   -----    65**</font>

#### 2.4.4 常见运算符

<font color=blue>**1. 自增自减运算符**</font>

```java
++  自增运算符
--  自减运算符
```

使用方式：

* 放在变量的前面，叫做先++。 比如：++a

* 放在变量的后面，叫做后++。 比如：a++

<font color=blue>**2. 赋值运算符**</font>

最为常用的：	 =

扩展赋值运算符:    +=、-=、*=、/=、%=

==注意==：扩展的赋值运算符中隐层还包含了一个强制转换

​	a += b ; 相当于 a = (byte)(a + b);

<font color=blue>**3. 关系运算符**</font>

又叫比较运算符，其实就是拿着左边跟右边进行了判断而已

| 符号 | 解释                                                         |
| ---- | ------------------------------------------------------------ |
| ==   | 就是判断左边跟右边是否相等，如果成立就是true，如果不成立就是false |
| !=   | 就是判断左边跟右边是否不相等，如果成立就是true，如果不成立就是false |
| >    | 就是判断左边是否大于右边，如果成立就是true，如果不成立就是false |
| >=   | 就是判断左边是否大于等于右边，如果成立就是true，如果不成立就是false |
| <    | 就是判断左边是否小于右边，如果成立就是true，如果不成立就是false |
| <=   | 就是判断左边是否小于等于右边，如果成立就是true，如果不成立就是false |

<font color=blue>**4. 逻辑运算符**</font>

**&：逻辑与（而且）**,两边都为真，结果才是真，只要有一个为假，那么结果就是假

**|：逻辑或（或者）**,两边都为假，结果才是假，只要有一个为真，那么结果就是真

**^（异或）**,如果两边相同，结果为false，如果两边不同，结果为true

**!（取反）**,false取反就是true，true取反就是false, <font color=red>**取反最多只用一个**</font>

短路逻辑运算符：**&&   ||**
- 逻辑核心：当左边不能确定整个表达式的结果，右边才会执行。当左边能确定整个表达式的结果，那么右边就不会执行了。从而提高了代码的运行效率
- 使用场景：用户登录。如果用户名输入正确了，那么再判断密码是否正确，是符合业务逻辑的，但是如果用户名输入错误，则没有必要再去比较密码

<font color=blue>**5. 三元运算符**</font>

**格式**：<font color=red>**关系表达式？表达式1：表达式2**</font>

**计算规则：**

* 如果关系表达式的值为真，那么执行表达式1
* 如果关系表达式的值为假，那么执行表达式2

==注意==：三元运算符的最终结果一定要被使用，要么赋值给一个变量，要么直接打印出来

**运算符的优先级**：<font color=red>**小括号优先所有**</font>	



### 2.5 原码、反码、补码

<font color=blue>**1. 原码：**</font>十进制数据的二进制表现形式，最左边为符号位，0为正，1为负

1个字节 = 8个bit

1个字节的最大值 = 0 1111111 = 127（符号位为0）

1个字节的最小值 = 1 1111111 = -127 (符号位为1)

<font color=blue>**2. 反码：**</font>正数的补码反码是其本身，<font color=red>**负数的反码是符号位保持不变，其余位取反**</font>

- 为了解决原码不能计算负数的问题出现的
- 弊端：负数运算时若结果跨0，跟实际结果会存在1的偏差

<font color=blue>**3. 补码：**</font>正数的补码是其本身，<font color=red>**负数的补码是在其反码的基础上+1**</font>

- 为了解决负数计算时跨0问题出现的
- ==注意==：计算机中存储和计算都是以补码的形式进行的

- 隐式转换：前面补0；强制转换：前面去0

<font color=blue>**4. 左移<<：**</font>向左移动，低位补0，<font color=red>**左移一次相当于*2**</font>

```java
int a = 200;
System.out.println(a << 2);

0000 0000 0000 0000 0000 0000 1100 1000
  00 0000 0000 0000 0000 0000 1100 1000 00  == 800  
```

<font color=blue>**5. 右移>>：**</font>向右移动，高位补0或1（符号位取决于原来数字的正负），<font color=red>**右移一次相当于/2**</font>

<font color=blue>**6. 无符号右移>>>：**</font>向右移动，高位补0



### 2.6 流程控制语句

<font color=blue>**流程控制语句分类：**</font>

- 顺序结构
- 判断和选择结构(if, switch)
- 循环结构(for, while, do…while)

#### 2.6.1 判断和选择结构

<font color=blue>**1. if 语句**</font>

```java
if (关系表达式) {
    语句体;	
}
```

==**细节**==：

- 如果要对一个布尔类型的变量进行判断，不用写==，**直接把变量写在小括号**中即可
- 如果大括号中的语句体只有一条，那么大括号可以**省略不写**，如果大括号省略了，那么if只能控制距离他最近的那一条语句

```java
if (关系表达式1) {
    语句体1;	
} else if (关系表达式2) {
    语句体2;	
} 
…
else {
    语句体n+1;
}
```

<font color=blue>**2. switch 语句**</font>

```java
switch (表达式) {
	case 1:
		语句体1;
		break;
	case 2:
		语句体2;
		break;
	...
	default:
		语句体n+1;
		break;
}
```

==**细节**==：

- default可以**放在任意位置**，也可以省略

- 不写break会引发<font color=red>**case穿透现象**</font>

- switch在JDK12的**新特性**


```java
int number = 10;
switch (number) {
    case 1 -> System.out.println("一");
    case 2 -> System.out.println("二");
    case 3 -> System.out.println("三");
    default -> System.out.println("其他");
}
```

<font color=blue>**3. switch 和 if 各自的使用场景**</font>

- 需要对一个**范围**进行判断的时候，用 **if**
- 把**有限个数据**列举出来，选择其中一个执行的时候，用**switch**语句
- 比如：小明的考试成绩，用switch需要写100个case，所以用if简单。如果是星期，月份，客服电话中0~9的功能选择就可以用switch

###### 练习：switch穿透、JDK12简化

==需求：键盘录入星期数，输出工作日、休息日。(1-5) 工作日，(6-7)休息日==

```java
//1.键盘录入星期数
Scanner sc = new Scanner(System.in);
System.out.println("请输入星期");
int week = sc.nextInt();
//2.利用switch进行匹配
----------------------------------------------------
利用case穿透简化代码
switch (week){
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        System.out.println("工作日");
        break;
    case 6:
    case 7:
        System.out.println("休息日");
        break;
    default:
        System.out.println("没有这个星期");
        break;
}
----------------------------------------------------
利用JDK12简化代码书写
switch (week) {
    case 1, 2, 3, 4, 5 -> System.out.println("工作日");
    case 6, 7 -> System.out.println("休息日");
    default -> System.out.println("没有这个星期");
}
```

#### 2.6.2 循环结构

<font color=blue>**1. for循环**</font>

循环语句可以在满足循环条件的情况下，反复执行某一段代码，这段被重复执行的代码被称为循环体语句，当反复执行这个循环体时，需要在合适的时候把循环判断条件修改为false，从而结束循环，否则循环将一直执行下去，形成死循环。

```java
for (初始化语句;条件判断语句;条件控制语句) {
	循环体语句;
}
```

<font color=blue>**2. while循环**</font>

```java
初始化语句;
while(条件判断语句){
	循环体;
	条件控制语句;
}
```

<font color=blue>**3. do...while循环**</font>

```java
初始化语句;
do{
    循环体;
    条件控制语句;
}while(条件判断语句);
```

<font color=blue>**4. 三种格式区别**</font>

- **判断顺序**：
  - for和while循环，是先判断，再执行
  - do...while是先执行，再判断

- **使用场景**：
  - 当知道循环次数或者循环范围的时候，用for循环
  - 当**不知道循环次数，也不知道循环范围**，只知道循环的结束条件时，用**while循环**


<font color=blue>**5. 无限循环、死循环**</font>

```java
for(;;){
    System.out.println("循环执行一直在打印内容");
}
```

```java
while(true){
    System.out.println("循环执行一直在打印内容");
}
```

```java
do{
    System.out.println("循环执行一直在打印内容");
}while(true);
```

==注意==：

- 最为常用的格式：while

* 无限循环下面不能再写其他代码了，因为永远执行不到

#### 2.6.3 条件控制

<font color=blue>**1. break**</font>

<font color=red>**不能单独存在**</font>的。可以用在**switch和循环**中。表示结束，跳出的意思

```java
//1.吃1~5号包子
for (int i = 1; i <= 5; i++) {
    System.out.println("在吃第" + i + "个包子");
    //2.吃完第三个的时候就不吃了
    if(i == 3){
        break;//结束整个循环
    }
}
```

<font color=blue>**2. continue**</font>

<font color=red>**不能单独存在**</font>，只能存在于**循环**当中。表示跳过本次循环，继续执行下次循环

```java
//1.吃1~5号包子
for (int i = 1; i <= 5; i++) {
    //2.第3个包子有虫子就跳过，继续吃下面的包子
    if(i == 3){
        //跳过本次循环（本次循环中，下面的代码就不执行了），继续执行下次循环
        continue;
    }
    System.out.println("在吃第" + i + "个包子");
}
```



### 2.7 Random

1. 导包

```java
import java.util.Random;
导包的动作必须出现在类定义的上边
```

2. 创建对象

```java
Random r = new Random ();
上面这个格式里面，只有r是变量名，可以变，其他的都不允许变
```

3. 生成随机数

```java
int number = r.nextInt(随机数的范围);
随机数范围的特点：从0开始，不包含指定值。比如：参数为10，生成的范围[0,10)
```

```java
//1.导包
import java.util.Random;

public class RandomDemo {
    public static void main(String[] args) {
        //2.创建对象
        Random r = new Random();
        //3.生成随机数
        int number = r.nextInt(100);//包左不包右，包头不包尾
        //0 ~ 99
        System.out.println(number);
    }
}
```



### 2.8 数组

<font color=blue>**1. 概念**</font>

数组容器在存储数据的时候，需要**结合隐式转换**考虑
- 定义了一个int类型的数组。那么boolean。double类型的数据是不能存到这个数组中
- 但是byte类型，short类型，int类型的数据是可以存到这个数组里面的

**建议**：容器的类，和存储的数据类型**保持一致**

<font color=blue>**2. 定义**</font>

```java
数据类型[] 数组名
```

```java
数据类型 数组名[]
```

<font color=blue>**3. 静态初始化**</font>

```java
数据类型[] 数组名 = new 数据类型[]{元素1，元素2，元素3，元素4...}
```

简化格式：

```java
数据类型[] 数组名 = {元素1，元素2，元素3，元素4...}
```

==注意==：

* 等号前后的数据类型必须保持一致

* 数组一旦创建之后，<font color=red>**长度不能发生变化**</font>

<font color=blue>**4. 地址值**</font>

```java
int[] arr = {1,2,3,4,5};
System.out.println(arr);//[I@6d03e736
```

打印数组的时候，实际出现的是数组的地址值，即数组在内存中的位置

以[I@6d03e736为例：

​	[ ：表示现在打印的是一个数组

​	I：表示现在打印的数组是int类型的

​	@：仅仅是一个间隔符号而已

6d03e736：就是数组在内存中真正的地址值（十六进制）

习惯性会把[I@6d03e736这个整体称之为数组的地址值

<font color=blue>**5. 数组的元素访问**</font>

```java
数组名[索引];
```

修改数组中对应索引上的值, 一旦修改之后，原来的值就会被覆盖了

<font color=blue>**6. 数组的遍历**</font>

数组的长度：数组名.length;

IDEA快捷键：<font color=red>**数组名.fori**</font>

<font color=blue>**7. 数组的动态初始化**</font>

```	java
数据类型[] 数组名 = new 数据类型[数组的长度];
```

```java
//1.定义一个数组，存3个人的年龄，年龄未知
int[] agesArr = new int[3];

//2.定义一个数组，存班级10名学生的考试成绩，考试成绩暂时未知，考完才知道。
int[] scoresArr = new int[10];
```

<font color=blue>**8. 数组的默认初始化值**</font>

​	整数类型：0

​	小数类型：0.0

​	<font color=red>**布尔类型：false**</font>

​	字符类型：'\u0000'

​	引用类型：null

<font color=blue>**9. 数组两种初始化方式的区别**</font>

- 静态初始化：int[] arr = {1,2,3,4,5}; 手动指定数组元素，系统会**根据元素个数计算出数组长度**

- 动态初始化：int[] arr = new int[3]; 手动指定数组长度，系统会给出默认初始值

###### 练习1：交换数据

==需求：定义一个数组，存入1,2,3,4,5。按照要求交换索引对应的元素==

```java
int[] arr = {1,2,3,4,5};
for(int i = 0,j = arr.length - 1; i < j; i++,j--){
    int temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

###### 练习2：打乱数据 

==需求：定义一个数组，存入1~5。要求打乱数组中所有数据的顺序==

```java
int[] arr = {1, 2, 3, 4, 5};
Random r = new Random();
for (int i = 0; i < arr.length; i++) {
    int randomIndex = r.nextInt(arr.length);
    int temp = arr[i];
    arr[i] = arr[randomIndex];
    arr[randomIndex] = temp;
}
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

###### 练习3：数组录入

==需求：有一个数组，其中有十个元素从小到大依次排列 {12,14,23,45,66,68,70,77,90,91}。再通过键盘录入一个整数数字。要求：把数字放入数组序列中，生成一个新的数组，并且数组的元素依旧是从小到大排列的。执行效果如下：==

```java
请输入一个整数数字：
50
生成的新数组是：12 14 23 45 50 66 68 70 77 90 91
```

```java
public class Demo {
    public static void main(String[] args) {        
        int[] arr = {12,14,23,45,66,68,70,77,90,91};
        int[] brr = new int[11];
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数数字");
        int num = sc.nextInt();
        int index = 0;
        for (int i = 0; i < arr.length; i++) {
            if(arr[i] <= num) {
                brr[i] = arr[i];
                index = i + 1;
            }else{
                brr[i+1] = arr[i];
            }
        }
        brr[index] = num;
        System.out.print("生成的新数组是：");
        for (int i = 0; i < brr.length; i++) {
            System.out.print(brr[i] + " ");
        }
    }
}
```

###### 练习4：奇偶比对

==需求：定义一个数组其中包含多个数字。用自己的方式最终实现，奇数放在数组的左边，偶数放在数组的右边==

```java
public class Demo {
    public static void main(String[] args) {
        int[] arr = {12,23,34,45,67,78,11,22};
        int[] brr = new int[arr.length];
        int left = 0;
        int right = arr.length-1;
        for (int i = 0; i < arr.length; i++) {
            if(arr[i] % 2 == 1){
                brr[left] = arr[i];
                left++;
            }else{
                brr[right] = arr[i];
                right--;
            }
        }
        for (int i = 0; i < brr.length; i++) {
            System.out.print(brr[i] + " ");
        }
    }
}
```

###### 练习5：验证码

==需求：定义方法实现随机产生一个5位的验证码。==

验证码格式：

​	长度为5

​	前四位是大写字母或者小写字母

​	最后一位是数字

```java
import java.util.Random;

public class Test {
    public static void main(String[] args) {
        //方法：在一堆没有什么规律的数据中随机抽取，可以先把这些数据放到数组中，再随机抽取一个索引

        //1.大写字母和小写字母都放到数组当中
        char[] chs = new char[52];
        for (int i = 0; i < chs.length; i++) {
            if(i <= 25){
                //添加小写字母 a --- 97
                chs[i] = (char)(97 + i);
            }else{
                //添加大写字母 A --- 65
                chs[i] = (char)(65 + i - 26);
            }
        }

        //定义一个字符串类型的变量，用来记录最终的结果
        String result = "";

        //2.随机抽取4次
        //随机抽取数组中的索引
        Random r = new Random();
        for (int i = 0; i < 4; i++) {
            int randomIndex = r.nextInt(chs.length);
            //利用随机索引，获取对应的元素
            result = result + chs[randomIndex];
        }
       
        //3.随机抽取一个数字0~9
        int number = r.nextInt(10);
        result = result + number;
        System.out.println(result);
    }
}
```

###### 拓展：二维数组

1. 二维数组静态初始化：

   ```java
   {% raw %}
   数组类型[][]数组名 = new 数组类型[][]{{元素1，元素2},{元素1，元素2}};
   {% endraw %}
   建议：将每一个一维数组单独写一行
       int[][] arr = {
       {1,2,3},
       {4,5,6,7,8}
   };
   ```

2. 元素访问：

   ```java
   数组名[索引][索引];
   ```

3. 二维数组遍历：

   ```java
   先得到一维数组，再遍历一维数组获取元素
   ```



### 2.9 方法

方法（method）是<font color=red>**程序中最小的执行单元**</font>

* 方法必须先创建才可以使用，该过程成为**方法定义**
* 方法创建后并不是直接可以运行的，需要手动使用后，才执行，该过程成为**方法调用**

#### 2.9.1 方法的定义和调用

<font color=blue>**1. 无参数方法 **</font>

```java
public static void 方法名 (   ) {
	// 方法体;
}
```

```java
方法名();
```

<font color=blue>**2. 带参数方法 **</font>

```java
public static void 方法名 (参数1) {
	方法体;
}

public static void 方法名 (参数1, 参数2, 参数3...) {
	方法体;
}
```

```java
方法名(参数)；

方法名(参数1,参数2);
```

**形参和实参：**

- 形参：方法定义中的参数 - 等同于**变量定义格式**，例如：int number
- 实参：方法调用中的参数 - 等同于**使用变量或者常量**，例如： 10  number

<font color=blue>**3. 带返回值方法 **</font>

```java
public static 数据类型 方法名 (参数) { 
	return 数据 ;
}
```

==注意==：方法定义时return后面的返回值与方法定义上的数据类型**要匹配**，否则程序将报错

```java
方法名 (参数) ;
数据类型 变量名 = 方法名 (参数) ;
```

==注意==：方法的返回值通常会<font color=red>**使用变量接收**</font>，否则该返回值将无意义

<font color=blue>**4. 方法的注意事项 **</font>

* 方法不能嵌套定义

  ```java
  public static void methodOne() {
      public static void methodTwo() {
          // 这里会引发编译错误!!!
      }
  }
  ```
  
* void表示无返回值，可以省略return，也可以单独的书写return，后面不加数据

  ```java
  public static void methodTwo() {
      //return 100; 编译错误，因为没有具体返回值类型
      return;	
      //System.out.println(100); return语句后面不能跟数据或代码
  }
  ```

#### 2.9.2 方法重载

<font color=blue>**1. 方法重载 **</font>：指同一个类中定义的多个方法之间的关系，满足下列条件的多个方法相互构成重载

* 多个方法在<font color=red>**同一个类中**</font>
* 多个方法具有<font color=red>**相同的方法名**</font>
* 多个方法的参数不相同，类型不同或者数量不同

<font color=blue>**2. 方法重载 **</font>

* 重载仅对应方法的定义，与方法的调用无关，调用方式参照标准格式
* 重载仅针对同一个类中方法的名称与参数进行识别，<font color=red>**与返回值无关**</font>，换句话说不能通过返回值来判定两个方法是否相互构成重载

###### 	练习1：整数是否相同

==需求：使用方法重载的思想，设计比较两个整数是否相同的方法，兼容全整数类型（byte,short,int,long)==

```java
public class MethodTest {
    public static void main(String[] args) {
        System.out.println(compare(10, 20));
        System.out.println(compare((byte) 10, (byte) 20));
        System.out.println(compare((short) 10, (short) 20));
        System.out.println(compare(10L, 20L));
    }

    public static boolean compare(int a, int b) {
        System.out.println("int");
        return a == b;
    }
    public static boolean compare(byte a, byte b) {
        System.out.println("byte");
        return a == b;
    }
    public static boolean compare(short a, short b) {
        System.out.println("short");
        return a == b;
    }
    public static boolean compare(long a, long b) {
        System.out.println("long");
        return a == b;
    }
}
```

###### 练习2：打印素数

==需求：判断101~200之间有多少个素数，并输出所有素数。==

素数：除了1和自身，无法被其他元素整除

```java
public class Test {
    public static void main(String[] args) {
        int count = 0;
        for (int i = 101; i <= 200; i++) {
            boolean flag = true;
            for (int j = 2; j < i; j++) {
                if(i % j == 0){
                    flag = false;
                    break;
                }
            }
            if(flag){
                System.out.println("当前数字"+i+"是质数");
                count++;
            }
        }
        System.out.println("一共有" + count + "个质数");
    }
}
```



### 2.10 Java的内存分配

<font color=blue>**1. 基本概念 **</font>

- **栈**：方法运行时使用的内存，比如main方法运行，进入方法栈中执行
  - **程序的主入口**(main方法)
  - 开始执行时会进入栈，代码执行完毕出栈
- **堆**：存储**对象或数组**，new来创建，都存储在堆内存
  - new来创建的，都存储在堆内存；只要是new出来的一定在堆中开辟了小空间
  - 若new了多次，堆中就有许多个小空间，每个小空间中有各自的数据
- **方法区**：存储可以运行的class文件
- **本地方法栈**：JVM在使用操作系统功能的时候使用，和开发无关
- **寄存器**：给CPU使用，和开发无关

<font color=blue>**2. 数组的内存 **</font>

![neicun](javaBasis_assets\3.png)

<font color=blue>**3. 引用数据类型和基本数据类型 **</font>

- 基本数据类型：整数类型、浮点数类型、布尔类型、字符类型

  - 变量中存储的是**真实**的数据

  - 数据存储在自己的空间中

  - 赋值给其他变量也是赋真实的值

- 引用数据类型：除以上其他所有类型

  - new出来的，变量中存储的是**地址值**

  - <font color=red>**数据存储在其他空间中，自己空间中存储的是地址值**</font>

  - 赋值给其他变量赋的是地址值

---



## 3 Java面向对象

### 3.1 类和对象

#### 3.1.1 类和对象的基本概念

类是对事物的一种描述，对象则为具体存在的事物

<font color=blue>**1. 类的定义**</font>

- 类的组成是由属性和行为两部分组成

  * **属性**：在类中通过<font color=red>**成员变量**</font>来体现（类中方法外的变量）

  * **行为**：在类中通过<font color=red>**成员方法**</font>来体现（和前面的方法相比去掉static关键字即可）


- 类的定义步骤：定义类、定义成员变量、定义成员方法

```java
public class 类名 {
	// 成员变量
	变量1的数据类型 变量1；
	变量2的数据类型 变量2;
	…
	// 成员方法
	方法1;
	方法2;	
}
```

- 示例代码：

```java
/*手机类：
   类名：手机(Phone)
   成员变量：
        品牌(brand)
        价格(price)
   成员方法：
        打电话(call)
        发短信(sendMessage)*/
public class Phone {
    //成员变量
    String brand;
    int price;

    //成员方法
    public void call() {
        System.out.println("打电话");
    }

    public void sendMessage() {
        System.out.println("发短信");
    }
}
```

<font color=blue>**2. 对象的使用**</font>

* 创建对象的格式：

  ```java
  类名 对象名 = new 类名();
  ```

* 调用成员的格式：

  ```java
  对象名.成员变量
  对象名.成员方法();
  ```

* 示例代码

```java
public class PhoneDemo {
    public static void main(String[] args) {
        //创建对象
        Phone p = new Phone();

        //使用成员变量
        System.out.println(p.brand);
        System.out.println(p.price);

        //使用成员方法
        p.call();
        p.sendMessage();
    }
}
```

#### 3.1.2 成员变量和局部变量

<font color=blue>**1. 类中位置不同**</font>

- 成员变量：类中方法外
- 局部变量：方法内部/方法声明上

<font color=blue>**2. 内存中位置不同**</font>

- <font color=red>**成员变量：堆内存**</font>
- <font color=red>**局部变量：栈内存**</font>

<font color=blue>**3. 生命周期不同**</font>

- 成员变量：随着对象存在而存在，随着对象消失而消失
- 局部变量：随着方法的调用而存在，方法调用完毕消失

<font color=blue>**4. 初始化值不同**</font>

- 成员变量：有默认初始化值
- 局部变量：没有默认初始化值，必须先定义，赋值才能使用

#### 3.1.3 对象的内存

- **Java内存分配**：栈、堆、方法区、本地方法栈、寄存器
- 从JDK8开始，取消方法区，新增元空间(将原方法区中多种功能进行拆分，有的功能放到堆，有的功能放到元空间)
  - 方法区：字节码文件加载时进入的内存```Test.class```
  - **栈内存**：<font color=red>**方法**</font>运行时所进入的内存，变量也在这里
  - **堆内存**：<font color=red>**new出来的东西**</font>会在这块内存中开辟空间并产生地址

<font color=blue>**1. 单个对象内存图**</font>

​	①：加载class文件

​	②：声明局部变量

​	③：在堆内存中开辟一个空间

​	④：默认初始化

​	⑤：显示初始化

​	⑥：构造方法初始化

​	⑦：将堆内存中的地址值赋值给左边的局部变量

* 成员变量使用过程

![1](javaBasis_assets\4.png)

* 成员方法调用过程

![2](javaBasis_assets\5.png)

<font color=blue>**2. 多个对象内存图**</font>

* 成员变量使用过程

![3](javaBasis_assets\6.png)

* 成员方法调用过程

![4](javaBasis_assets\7.png)

==总结：==多个对象在堆内存中，都有不同的内存划分，成员变量存储在各自的内存区域中，**成员方法多个对象共用的一份**

<font color=blue>**3. 基本数据类型与引用数据类型**</font>

- 基本数据类型

  - **自己玩自己的，与其他没有关系**

  - 从内存角度理解：数据值是存储在自己的空间，赋值给其他变量，也是赋的真实值

<img src="javaBasis_assets\8.png" alt="image-20240627103522224" style="zoom: 33%;" />

- 引用数据类型
  - **拿别人的东西过来用，存储的是地址值**
  - 从内存角度理解：数据值是存储在其他空间中，自己空间中存储的是地址值，赋值给其他变量，赋的是地址值

<img src="javaBasis_assets\9.png" alt="image-20240627103705261" style="zoom:33%;" />

#### 3.1.4 this 的内存原理

![image-20240627104446558](javaBasis_assets\10.png)



### 3.2 封装

#### 3.2.1 封装思想

<font color=blue>**1. 封装概述**</font>

- 是面向对象三大特征之一（**封装，继承，多态**）

- <font color=red>**对象代表什么，就得封装对应的数据，并提供数据对应的行为** </font>

<font color=blue>**2. 封装代码实现**</font>

- 将类的某些信息**隐藏在类的内部**，不允许外部程序直接访问，通过该类提供的方法对隐藏信息操作和访问
- <font color=red>**成员变量private，提供对应的getxxx()/setxxx()方法**</font>

#### 3.2.2 private关键字

private是一个修饰符，可以用来修饰成员（成员变量，成员方法）

* 被private修饰的成员，只能在本类进行访问，针对private修饰的成员变量，如果需要被其他类使用，提供相应的操作

  * 提供“get变量名()”方法，用于<font color=red>**获取**</font>成员变量的值，方法用public修饰
  * 提供“set变量名(参数)”方法，用于<font color=red>**设置**</font>成员变量的值，方法用public修饰

* 示例代码：

  ```java
  class Student {
      String name;
      private int age;
  
      //提供get/set方法
      public void setAge(int a) {
          if(a<0 || a>120) {
              System.out.println("你给的年龄有误");
          } else {
              age = a;
          }
      }
      public int getAge() {
          return age;
      }
      
      //成员方法
      public void show() {
          System.out.println(name + "," + age);
      }
  }
  
  /*学生测试类*/
  public class StudentDemo {
      public static void main(String[] args) {
          //创建对象
          Student s = new Student();
          //给成员变量赋值
          s.name = "林青霞";
          s.setAge(30);
          s.show();
      }
  }
  ```

#### 3.2.3 this关键字

this修饰的变量用于指代**成员变量**，其主要作用是（**区分局部变量和成员变量的重名问题）**

* 方法的形参如果与成员变量同名，不带this修饰的变量指的是形参，而不是成员变量
* 方法的形参没有与成员变量同名，不带this修饰的变量指的是成员变量

<font color=red>**this的本质：代表方法调用者的地址值**</font>



### 3.3 构造方法

#### 3.3.1 构造方法概述

<font color=blue>**1. 构造方法作用**</font>

创建对象时，由虚拟机自动调用，<font color=red>**给成员变量进行初始化**</font>

- **无参构造方法**：初始化对象时，成员变量的数据均采用**默认值**
- **有参构造方法**：初始化对象时，同时给对象**赋值**

<font color=blue>**2. 格式**</font>

```java
修饰符 类名(参数){
}
```

<font color=blue>**3. 示例代码**</font>

```java
class Student {
    private String name;
    private int age;

    //构造方法
    public Student() {
        System.out.println("无参构造方法");
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*测试类*/
public class StudentDemo {
    public static void main(String[] args) {
        Student s = new Student();
        s.show();
    }
}
```

<font color=blue>**4. 注意事项**</font>

- **构造方法的创建**
  - 若没有定义：系统给出**默认的无参**构造方法
  - 若定义了：系统不再提供默认的构造方法
- **构造方法的重载**
  - 若定义了有参构造方法，还需要使用无参构造方法，必须再写一个无参构造方法
- 推荐：<font color=red>**无论是否使用，都手动添加无参构造方法**</font>

* **快捷键：**

  ①：Generate

  ②：安装插件

  <img src="javaBasis_assets\11.png" alt="8" style="zoom:50%;" />

  <img src="javaBasis_assets\12.png" alt="9" style="zoom:50%;" />

* 示例代码

```java
class Student {
    private String name;
    private int age;

    public Student() {}
    public Student(String name) {
        this.name = name;
    }
    public Student(int age) {
        this.age = age;
    }
    public Student(String name,int age) {
        this.name = name;
        this.age = age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*测试类*/
public class StudentDemo {
    public static void main(String[] args) {
        //创建对象
        Student s1 = new Student();
        s1.show();

        //public Student(String name)
        Student s2 = new Student("林青霞");
        s2.show();

        //public Student(int age)
        Student s3 = new Student(30);
        s3.show();

        //public Student(String name,int age)
        Student s4 = new Student("林青霞",30);
        s4.show();
    }
}
```

#### 3.3.2 标准Javabean

- 类名需要**见名知意**

- 成员变量使用**private**修饰

- 提供至少两个**构造方法** 

  * 无参构造方法

  * 带全部参数的构造方法


- get和set方法 
  - 提供每一个成员变量对应的setXxx()/getXxx()

- 如果还有其他行为，也需要写上

示例代码：

```java
class Student {
    //成员变量
    private String name;
    private int age;

    //构造方法
    public Student() {
    }
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    //成员方法
    public void setName(String name) {
        this.name = name;
    }
    public String getName() {
        return name;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public int getAge() {
        return age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*创建对象并为其成员变量赋值的两种方式
        1:无参构造方法创建对象后使用setXxx()赋值
        2:使用带参构造方法直接创建带有属性值的对象*/
public class StudentDemo {
    public static void main(String[] args) {
        //无参构造方法创建对象后使用setXxx()赋值
        Student s1 = new Student();
        s1.setName("林青霞");
        s1.setAge(30);
        s1.show();

        //使用带参构造方法直接创建带有属性值的对象
        Student s2 = new Student("林青霞",30);
        s2.show();
    }
}
```



### 3.4 static关键字

#### 3.4.1 概述

<font color=blue>**1. Java通过static关键字来区分变量和方法**</font>

- <font color=red>**被static修饰**</font>的成员<font color=red>**属于类**</font>，放在静态区
- **没有**被修饰的成员属于**对象**

<font color=blue>**2.静态变量**</font>

- 被static修饰的成员变量 == 静态变量
- 特点：**被该类的所有对象共享**
- 调用方法：
  - 类名调用
  - 对象名调用
- **静态变量随着类的加载而加载，优先于对象出现**

<font color=blue>**3.静态方法**</font>

- 被static修饰的成员方法 == 静态方法
- 特点：多用在测试类和工具类中，Javabean中很少使用
- 调用方法：
  - 类名调用
  - 对象名调用

<font color=blue>**4.static内存图**</font>

JDK8之前静态区在方法区中，JDK8之后，放置在<font color=red>**堆空间**</font>中

![image-20240628182435586](javaBasis_assets\13.png)

<font color=blue>**5. 定义**</font>

```java
修饰符 static 数据类型 变量名 = 初始值；    
```

```java
public class Student {
    public static String schoolName = "东南大学"； // 属于类，只有一份
}
```

<font color=blue>**6. 注意事项**</font>

- **访问范围**
  - 静态方法：只能访问静态变量和静态方法
  - 非静态方法：可访问所有
- <font color=red>**静态中没有this关键字**</font>
  - static修饰的成员属于类，存储在静态区，随着类的加载而加载，并且只加载一次，所以只有一份，节省内存。所以可直接被类名调用，优先于对象存在，所以可被所有对象共享
  - 无static修饰的成员，属于对象，对象有多少个，他们就有多少份，所以必须由对象调用

- **重新认识main方法**
  - **public**：被JVM调用，访问权限足够大
  - **static**：被JVM调用，不用创建对象，直接类名访问，并且main方法是静态的，所以测试类中其他方法也需要用静态修饰，否则无法被main方法访问
  - **void**：被JVM调用，不需要给JVM返回值
  - **main**：通用名称，虽然不是关键字，但是只有main能被JVM识别
  - String[] args：以前用于接收键盘录入数据的，现在没用

#### 3.4.2 访问

<font color=blue>**1. 静态成员变量的访问**</font>

格式：**<font color=red>类名.</font>静态变量**

```java
Student.schoolName = "黑马程序员";
```

<font color=blue>**2. 实例变量的访问**</font>

实例变量：无static修饰的成员变量，属于每个对象，必须**创建类的对象才可以访问**

格式：**<font color=red>对象.</font>实例成员变量**

<font color=blue>**3. 静态方法的访问**</font>

因为类只有一个，所以静态方法在内存区域中也只存在一份，**所有对象均可共享**这个方法

格式：**<font color=red>类名.</font>方法名称**

```java
Student.study();
```

<font color=blue>**4. 实例方法的访问**</font>

实例方法：无static修饰的成员方法，属于每个对象，必须创建类的对象才能访问

格式：**<font color=red>对象.</font>实例方法**



### 3.5 继承 

#### 3.5.1 继承思想

**抽类**：将多个类中的相同属性和行为抽取到单独一个类中  == **父类、超类、基类**

**继承**：多个类无需再定义属性和行为，继承此类即可          == **子类**

<font color=blue>**1. 概念**</font>	

- 子类继承父类的**属性**和**行为**，使得子类对象可以直接具有与父类相同的属性、行为
- 子类可以直接**访问**父类中的<font color=red>**非私有**</font>的属性和行为

<font color=blue>**2. 作用**</font>

提高**代码的复用性**（减少代码冗余，相同代码重复利用）。使类与类之间产生了关系。

<font color=blue>**3. 定义**</font>

通过<font color=red>**extends**</font>关键字，可以声明一个子类继承另外一个父类，定义格式如下：

```java
class 父类 {
	...
}

class 子类 extends 父类 {
	...
}
```

**==注意==：Java是单继承的，一个类只能继承一个直接父类，跟现实世界很像，但支持多层继承**

​	   **每一个类都直接或间接继承于Object**

<font color=blue>**4. 子类不能继承的内容**</font>

- 子类**不能**继承父类的**构造方法**
- 子类<font color=red>**可以继承**</font>父类的**私有成员（成员变量，方法）**，只是子类<font color=red>**无法直接访问**</font>而已，可以通过getter/setter方法访问父类的private成员变量
- 子类<font color=red>**只可以继承**</font>父类中的**虚方法**(<font color=red>**未被private修饰的成员方法**</font>)

<img src="javaBasis_assets\14.png" alt="image-20240628205219686" style="zoom: 50%;" />

<font color=blue>**5. 继承的内存图**</font>

![image-20240628203954554](javaBasis_assets\15.png)

![image-20240628205137693](javaBasis_assets\16.png)

#### 3.5.2 继承后的成员变量

<font color=blue>**1. 成员变量重名**</font>

- 如果子类父类中出现**不重名**的成员变量，这时的访问是**没有影响的**

- 如果子类父类中出现**重名**的成员变量，这时的访问是**有影响的**。**子类会优先访问自己对象中的成员变量**

<font color=blue>**2. super访问父类成员变量**</font>

子父类中出现了同名的成员变量时，在子类中需要访问父类中**非私有**成员变量时，需要使用`super` 关键字，修饰父类成员变量，类似于之前的 `this` 。

==注意==：**super代表的是父类对象的引用，this代表的是当前对象的引用**

```java
super.父类成员变量名
```

子类方法需要修改，代码如下：

```java
class Fu {
	int num = 5;
}

class Zi extends Fu {
	int num = 6;
  
	public void show() {
        int num = 1;
        System.out.println("method num=" + num);  //1
        System.out.println("Zi num=" + this.num); //6
        System.out.println("Fu num=" + super.num);//5
	}
}
```

> 注意：Fu 类中的成员变量是非私有的，子类中可以直接访问。若Fu 类中的成员变量私有了，子类是不能直接访问的。通常编码时，我们遵循封装的原则，使用private修饰成员变量，那么如何访问父类的私有成员变量呢？**可以在父类中提供公共的getXxx方法和setXxx方法**

#### 3.5.3 继承后的成员方法

<font color=blue>**1. 成员方法重名**</font>

如果子类父类中出现**不重名**的成员方法，这时的调用是**没有影响的**。对象调用方法时，会先在子类中查找有没有对应的方法，若子类中存在就会执行子类中的方法，若子类中不存在就会执行父类中相应的方法

如果子类父类中出现**重名**的成员方法，则创建子类对象调用该方法的时候，**子类对象会优先调用自己的方法**

<font color=blue>**2. 方法重写**</font>

- **方法重写** ：子类中出现与父类一模一样的方法时（返回值类型，方法名和参数列表都相同），会出现覆盖效果，也称为重写或者复写。<font color=red>**声明不变，重新实现**</font>

- **何时使用**：发生在子父类之间的关系，子类继承了父类的方法，但是子类觉得父类的这方法不足以满足自己的需求，子类重新写了一个与父类同名的方法，以便覆盖父类的该方 法。

例如：定义了一个动物类

```java
public class Animal  {
    public void cry(){
        System.out.println("动物都可以叫~~~");
    }
}
```

然后定义一个猫类，猫可能认为父类cry()方法不能满足自己的需求

```java
public class Cat extends Animal {
    public void cry(){
        System.out.println("我们一起学猫叫，喵喵喵！喵的非常好听！");
    }
}
```

<font color=blue>**3. @Override重写注解**</font>

* 放在重写后的方法上的，**检验子类重写时语法是否正确**，这个注解标记的方法，就说明这个方法必须是重写父类的方法，否则编译阶段报错

* <font color=red>**建议重写都加上这个注解**</font>，一方面可以提高代码的可读性，一方面可以防止重写出错！

==**注意事项**==：

- 方法重写是发生在子父类之间的关系
- 子类方法覆盖父类方法，必须要保证<font color=red>**权限大于等于父类权限**</font>(空着不写<protected<public)
- 子类方法覆盖父类方法，返回值类型、函数名和参数列表都要**一模一样**
- 只有被添加到虚方法表中的方法才能被重写

#### 3.5.4 继承后的构造方法

<font color=blue>**1. 子类无法继承父类构造方法**</font>

- 表面原因：构造方法的名字是与类名一致的
- 实际原因：构造方法的作用是初始化对象成员变量。所以子类的初始化过程中，必须先执行父类的初始化动作。子类的构造方法中默认有一个`super()` ，表示调用父类的构造方法，父类成员变量初始化后，才可以给子类使用。（**先有爸爸，才能有儿子**）

<font color=blue>**2. 继承后子类构造方法**</font>

- 子类所有构造方法的第一行都会<font color=red>**默认先调用父类的无参构造方法**</font>，再执行自己
  - 因为：父类中的无参构造本质是对其属性进行默认初始化，如果子类中没有先默认调用父类的无参构造，**子类在继承父类中的属性时便无法使用父类的数据**

- 子类初始化前，一定要调用父类构造方法先完成父类数据空间初始化：**super()，不写也存在，必须在第一行**

**==注意==：** **super() 和 this() 都必须是在构造方法的第一行，所以<font color=red>不能同时出现</font>。**

<font color=blue>**3. super(...)案例图解**</font>

- **父类空间优先于子类对象产生**

在每次创建子类对象时，先初始化父类空间，再创建其子类对象本身。目的在于子类对象中包含了其对应的父类空间，便可以包含其父类的成员，如果父类成员非private修饰，则子类可以随意使用父类成员。代码体现在子类的构造器调用时，一定先调用父类的构造方法。理解图解如下：

<img src="javaBasis_assets\17.jpg" style="zoom: 67%;" />

<font color=blue>**4. 小结**</font>

* **子类的每个构造方法中均有默认的super()，调用父类的空参构造。手动调用父类构造会覆盖默认的super()。**

* **super() 和 this() 都必须是在构造方法的第一行，所以不能同时出现。**

* **super(..)和this(...)是根据参数去确定调用父类哪个构造方法的。**
* super(..)可以调用父类构造方法初始化继承自父类的成员变量的数据。
* this(..)可以调用本类中的其他构造方法。

示例代码：

```java
class Person {
    private String name;
    private int age;

    public Person() {
        System.out.println("父类无参");
    }
    // getter/setter省略
}

class Student extends Person {
    private double score;

    public Student() {
        //super(); // 调用父类无参,默认就存在，可以不写，必须在第一行
        System.out.println("子类无参");
    }
    
     public Student(double score) {
        //super();  // 调用父类无参,默认就存在，可以不写，必须在第一行
        this.score = score;    
        System.out.println("子类有参");
     }
}

public class Demo {
    public static void main(String[] args) {
        Student s1 = new Student();
        System.out.println("----------");
        Student s2 = new Student(99.9);
    }
}

输出结果：
父类无参
子类无参
----------
父类无参
子类有参
```



### 3.6 多态

#### 3.6.1 多态思想

<img src="javaBasis_assets\18.png" alt="image-20240628213759494" style="zoom: 50%;" />

<font color=blue>**1. 概念**</font>	

- **多态**：出现在继承/实现关系中，意味着<font color=red>**同类型的对象，表现出不同形态**</font>

- **前提**：<font color=red>**有继承关系**</font>，子类对象可以赋值给父类类型的变量。例如Animal是一个动物类型，而Cat是一个猫类型。Cat继承了Animal，Cat对象也是Animal类型，自然可以赋值给父类类型的变量

<font color=blue>**2. 格式**</font>	

```java
父类类型 变量名 = new 子类/实现类构造器;
变量名.方法名();
```

<font color=blue>**3. 多态的使用场景**</font>

如果没有多态，在下图中register方法只能传递学生对象，其他的Teacher和administrator对象是无法传递给register方法的，在这种情况下，只能定义三个不同的register方法分别接收学生，老师和管理员。

<img src="javaBasis_assets\19.png" alt="多态的应用场景" style="zoom:50%;" />

有了多态之后，方法的形参就可以定义为**共同的父类Person**

**==注意==：**

* 当一个方法的形参是一个类，可以传递这个类所有的**子类对象**
* 当一个方法的形参是一个接口，可以传递这个接口所有的**实现类对象**
* 多态还可以**根据传递的不同对象来调用不同类中的方法**

<img src="javaBasis_assets\20.png" alt="多态的应用场景" style="zoom:50%;" />

<font color=blue>**4. 多态的使用示例**</font>

```java
public class Test {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("张三");
        s.setAge(18);

        Teacher t = new Teacher();
        t.setName("王建国");
        t.setAge(30);

        Administrator admin = new Administrator();
        admin.setName("管理员");
        admin.setAge(35);

        register(s);
        register(t);
        register(admin);
    }
    
    public static void register(Person p){
        p.show();
    }
}
```

```java
public class Person {
    private String name;
    private int age;

    ...
    public void show(){
        System.out.println(name + ", " + age);
    }
}

public class Administrator extends Person {
    @Override
    public void show() {
        System.out.println("管理员的信息为：" + getName() + ", " + getAge());
    }
}

public class Student extends Person{
    @Override
    public void show() {
        System.out.println("学生的信息为：" + getName() + ", " + getAge());
    }
}

public class Teacher extends Person{
    @Override
    public void show() {
        System.out.println("老师的信息为：" + getName() + ", " + getAge());
    }
}
```

#### 3.6.2 多态特点

<font color=blue>**1. 使用的前提**</font>

- 有继承或者实现关系
- 方法的<font color=red>**重写**</font>【**意义体现**：不重写，无意义】
- <font color=red>**父类引用指向子类对象**</font>【**格式体现**】

> 父类类型：指子类对象继承的父类类型，或者实现的父接口类型。

<font color=blue>**2. 运行的特点**</font>

- 调用成员变量：编译看**左**边，运行看**左**边
  - 在子类的对象中，会把父类的成员变量也继承下来，调用则调用父类的
  - 编译：会先检查父类，若没有则不继续运行
- 调用成员方法：编译看**左**边，运行看**右**边
  - 若子类对方法进行重写，则虚方法表中会把父类的方法进行覆盖
  - 编译：**会先检查父类，若没有则不继续运行**

```java
Fu f = new Zi()；
//编译看左边的父类中有没有name这个属性，没有就报错
//在实际运行的时候，把父类name属性的值打印出来
System.out.println(f.name);  //Fu 
//编译看左边的父类中有没有show这个方法，没有就报错
//在实际运行的时候，运行的是子类中的show方法
f.show();  //Zi中的show方法
```

<font color=blue>**3. 多态的弊端**</font>

多态编译阶段是看左边父类类型的，如果子类有些独有的功能，此时<font color=red>**多态的写法无法访问子类独有功能**</font>

```java 
class Animal{
    public  void eat(){
        System.out.println("动物吃东西！")
	}
}
class Cat extends Animal {  
    public void eat() {  
        System.out.println("吃鱼");  
    }  
    public void catchMouse() {  
        System.out.println("抓老鼠");  
    }  
}  

class Dog extends Animal {  
    public void eat() {  
        System.out.println("吃骨头");  
    }  
}
 
class Test{
    public static void main(String[] args){
        Animal a = new Cat();
        a.eat();
        a.catchMouse();  //编译报错，编译看左边，Animal没有这个方法
    }
}
```

#### 3.6.3 引用类型转换

<font color=blue>**1. 为什么要转型？**</font>

**多态的写法无法访问子类独有功能**：当使用多态方式调用方法时，首先检查父类中是否有该方法，如果没有，则编译错误。也就是说，<font color=red>**不能调用子类拥有，而父类没有的方法**</font>。编译都错误，更别说运行。所以，想要调用子类特有的方法，必须做<font color=red>**向下转型**</font>。

<font color=blue>**2. 向上转型(自动转换)**</font>

- **向上转型**：多态本身是子类类型向父类类型向上转换（自动转换）的过程，这个过程是**默认的**
- 当父类引用指向一个子类对象时，便是向上转型
- **使用格式：**

```java
父类类型  变量名 = new 子类类型();
如：Animal a = new Cat();
```

> 原因：父类类型相对与子类来说是大范围的类型，Animal是动物类，是父类类型。Cat是猫类，是子类类型。Animal类型的范围当然很大，包含一切动物。所以子类范围小可以直接自动转型给父类类型的变量。
>

<font color=blue>**3. 向下转型(强制转换)**</font>

- **向下转型**：父类类型向子类类型向下转换的过程，这个过程是**强制**的。

- 一个已经向上转型的子类对象，将父类引用转为子类引用，可以使用**强制类型转换**的格式，便是向下转型。

  <font color=red>**想要调用子类特有的方法，必须做向下转型**</font>

- **使用格式**：

```java
子类类型 变量名 = (子类类型) 父类变量名;
如:Aniaml a = new Cat();
   Cat c =(Cat) a;  
```

#### 3.6.4 instanceof关键字

<font color=blue>**1. 转型的异常**</font>

转型的过程中，一不小心就会遇到这样的问题，请看如下代码：

```java
public class Test {
    public static void main(String[] args) {
        // 向上转型  
        Animal a = new Cat();  
        a.eat();               // 调用的是 Cat 的 eat

        // 向下转型  
        Dog d = (Dog)a;       
        d.watchHouse();        // 调用的是 Dog 的 watchHouse 【运行报错】
    }  
}
```

这段代码可以通过编译，但是运行时，却报出了 `ClassCastException` ，类型转换异常！这是因为，明明创建了Cat类型对象，运行时，当然不能转换成Dog对象。

<font color=blue>**2. instanceof关键字**</font>

为了避免ClassCastException的发生，Java提供了 `instanceof` 关键字，给引用变量做**类型的校验**，格式如下：

```java
变量名 instanceof 数据类型 
如果变量属于该数据类型或者其子类类型，返回true
如果变量不属于该数据类型或者其子类类型，返回false    
```

<font color=red>**在向下转型时，先使用instanceof关键字判别**</font>

```java
public class Test {
    public static void main(String[] args) {
        // 向上转型  
        Animal a = new Cat();  
        a.eat();               // 调用的是 Cat 的 eat

        // 向下转型  
        if (a instanceof Cat){
            Cat c = (Cat)a;       
            c.catchMouse();        // 调用的是 Cat 的 catchMouse
        } else if (a instanceof Dog){
            Dog d = (Dog)a;       
            d.watchHouse();       // 调用的是 Dog 的 watchHouse
        }
    }  
}
```

<font color=blue>**2. instanceof新特性**</font>

JDK14的时候提出了新特性，**把判断和强转合并成一行**

```java
变量名 instanceof 数据类型 新的变量名
```

```java
//先判断a是否为Dog类型，如果是，则强转成Dog类型，转换之后变量名为d
//如果不是，则不强转，结果直接是false
if(a instanceof Dog d){
    d.lookHome();
}else if(a instanceof Cat c){
    c.catchMouse();
}else{
    System.out.println("没有这个类型，无法转换");
}
```

###### 练习：多态综合练习

```java
1.定义狗类
    属性：年龄，颜色
    行为:eat(String something)(something表示吃的东西)
		看家lookHome方法(无参数)
2.定义猫类
	属性：年龄，颜色
	行为:eat(String something)方法(something表示吃的东西)
		逮老鼠catchMouse方法(无参数)
3.定义Person类//饲养员
	属性：姓名，年龄
	行为： keepPet(Dog dog,String something)方法
		  功能：喂养宠物狗，something表示喂养的东西
	行为： keepPet(Cat cat,String something)方法
		  功能：喂养宠物猫，something表示喂养的东西
	生成空参有参构造，set和get方法  
4.定义测试类(完成以下打印效果):
	keepPet(Dog dog,String somethind)方法打印内容如下：
		年龄为30岁的老王养了一只黑颜色的2岁的狗
		2岁的黑颜色的狗两只前腿死死的抱住骨头猛吃
	keepPet(Cat cat,String somethind)方法打印内容如下：
		年龄为25岁的老李养了一只灰颜色的3岁的猫
		3岁的灰颜色的猫眯着眼睛侧着头吃鱼
5.思考：		
	1.Dog和Cat都是Animal的子类，针对不同的动物，定义不同的keepPet方法，能否简化，并体会简化后的好处？
	2.Dog和Cat虽然都是Animal的子类，但是都有其特有方法，能否想办法在keepPet中调用特有方法？
```

代码示例：

```java
//动物类（父类）
public class Animal {
    private int age;
    private String color;

    public Animal() {}
    public Animal(int age, String color) {this.age = age;this.color = color;}
    public int getAge() {return age;}
    public void setAge(int age) {this.age = age;}
    public String getColor() {return color;}
    public void setColor(String color) {this.color = color;}
    public void eat(String something){System.out.println("动物在吃" + something);}
}

//猫类（子类）
public class Cat extends Animal {
    public Cat() {}
    public Cat(int age, String color) {super(age, color);}

    @Override
    public void eat(String something) {
        System.out.println(getAge() + "岁的" + getColor() + "颜色的猫眯着眼睛侧着头吃" + something);
    }
    public void catchMouse(){
        System.out.println("猫抓老鼠");
    }
}

//狗类（子类）
public class Dog extends Animal {
    public Dog() {}
    public Dog(int age, String color) {super(age, color);}

    @Override
    public void eat(String something) {
        System.out.println(getAge() + "岁的" + getColor() + "颜色的狗两只前腿死死的抱住" + something + "猛吃");
    }
    public void lookHome(){
        System.out.println("狗在看家");
    }
}

//饲养员类
public class Person {
    private String name;
    private int age;

    public Person() {}
    public Person(String name, int age) {this.name = name;this.age = age;}
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public int getAge() {return age;}
	public void setAge(int age) {this.age = age;}

    //想要一个方法，接收所有的动物，可以写这些类的父类 Animal
    public void keepPet(Animal a, String something) {
        if(a instanceof Dog d){
            System.out.println("年龄为" + age + "岁的" + name + "养了一只" + a.getColor() + "颜色的" + a.getAge() + "岁的狗");
            d.eat(something);
        }else if(a instanceof Cat c){
            System.out.println("年龄为" + age + "岁的" + name + "养了一只" + c.getColor() + "颜色的" + c.getAge() + "岁的猫");
            c.eat(something);
        }else{
            System.out.println("没有这种动物");
        }
    }
}

//测试类
public class Test {
    public static void main(String[] args) {
        Person p = new Person("老王",30);
        Dog d = new Dog(2,"黑");
        Cat c = new Cat(3,"灰");
        p.keepPet(d,"骨头");
        p.keepPet(c,"鱼");
    }
}
```



### 3.7 抽象类

#### 3.7.1 权限修饰符

Java中提供了**四种访问权限**，使用不同的访问权限修饰符修饰时，被修饰的内容会有不同的访问权限

- **public**：公共的，所有地方都可以访问

- **protected**：本类 ，本包，<font color=red>**其他包中的子类都可以访问**</font>

- **默认**（没有修饰符）：本类 ，本包可以访问; 默认是空着不写，不是default

- **private**：私有的，当前类可以访问
  `public > protected > 默认 > private`

|                  | public | protected | 默认 | private |
| ---------------- | ------ | --------- | ---- | ------- |
| 同一类中         | √      | √         | √    | √       |
| 同一包中的类     | √      | √         | √    |         |
| 不同包的子类     | √      | √         |      |         |
| 不同包中的无关类 | √      |           |      |         |

<font color=red>**建议这样使用权限：**</font>

- 成员变量使用`private` ，隐藏细节
- 构造方法使用` public` ，方便创建对象
- 成员方法使用`public` ，方便调用方法

#### 3.7.2 final关键字

**final**：  不可改变，表示修饰的内容不可变

<font color=blue>**1. final修饰类**</font>

被修饰的类，<font color=red>**不能被继承**</font>

```java
final class 类名 {
}
```

> 查询API发现像 `public final class String` 、`public final class Math` 、`public final class Scanner` 等，很多都是被final修饰的，目的就是供使用，而不让改变其内容

<font color=blue>**2. final修饰方法**</font>

被修饰的方法，<font color=red>**不能被重写**</font>，**方法是一种规则，不希望别人去改变**

```java
修饰符 final 返回值类型 方法名(参数列表){
    //方法体
}
```

<font color=blue>**3. final修饰变量**</font>

被修饰的变量，<font color=red>**有且仅能被赋值一次**</font>

- **局部变量——基本类型**

==思考：下面两种写法，哪种可以通过编译？==

写法1：

```java
final int c = 0;
for (int i = 0; i < 10; i++) {
    c = i;
    System.out.println(c);
}
```

写法2：

```java
for (int i = 0; i < 10; i++) {
    final int c = i;
    System.out.println(c);
}
```

根据 `final` 的定义，写法1报错，写法2通过编译。因为每次循环，都是一次新的变量c

- **成员变量**

  - 显示初始化(在定义成员变量的时候立马赋值)（常用）

    ```java
    public class Student {
        final int num = 10;
    }
    ```

  - 构造方法初始化(在构造方法中赋值一次)（不常用，了解即可）

    **==注意==：每个构造方法中都要赋值一次！**

    ```java
    public class Student {
        final int num = 10;
        final int num2;
    
        public Student() {
            this.num2 = 20;
        }
        
         public Student(String name) {
            this.num2 = 20;
        }
    }
    ```


<font color=blue>**4. 命名规范**</font>

> 被final修饰的常量名称，一般都有书写规范，所有字母都<font color=red>**大写**</font>

- 单个单词：全部大写

- 多个单词：全部大写，**单词之间用下划线**隔开

- final修饰的变量是基本类型，变量存储的数据值不能发生改变；

  final修饰的变量是引用类型，变量存储的**地址值不能发生改变**，对象内部的(属性值)可以改变

  ```java
  final double PI = 3.14;
  //创建对象
  final Student S = new Student("zhangsan",23);
  S.setName("李四");//记录的地址值不能改变，但内部的属性值可以改变
  S.setAge(24);
  ```

#### 3.7.3 代码块

<font color=blue>**1. 局部代码块**</font>

- 方法中的代码块
- 作用：提前结束变量的生命周期

<font color=blue>**2. 构造代码块**</font>

- 写在成员位置的代码块

- 作用：将构造方法中重复的代码抽取出来
- 执行时机：在创建本类对象时会先执行构造代码块再执行构造方法

<font color=blue>**3. 静态代码块**</font>

- 随着类的加载而加载，并且只执行一次
- 作用：进行**数据初始化**



#### 3.7.4 抽象类和抽象方法

​	父类中的方法，被它的子类们重写，子类各自的实现都不尽相同。那么父类的方法声明和方法主体，只有声明还有意义，而方法主体则没有存在的意义了(因为子类对象会调用自己重写的方法)。换句话说，父类可能知道子类应该有哪个功能，但是功能具体怎么实现父类是不清楚的（由子类自己决定），父类只需要提供一个没有方法体的定义即可，具体实现交给子类自己去实现。**把没有方法体的方法称为抽象方法。Java语法规定，包含抽象方法的类就是抽象类**。

<font color=blue>**1. 抽象方法**</font>

- 定义：<font color=red>**没有方法体的方法**</font>

- 格式：

  ```java
  修饰符 abstract 返回值类型 方法名 (参数列表)；
  ```

<font color=blue>**2. 抽象类**</font>

- 定义：<font color=red>**包含抽象方法的类**</font>

- 格式：

  ```java
  abstract class 类名字 { 
  }
  ```

  **==注意==：抽象类不一定有抽象方法，但是有抽象方法的类必须定义成抽象类**

- 使用：继承抽象类的子类**必须重写父类所有的抽象方法**。否则，该子类也必须声明为抽象类
  - 实现方法：**方法重写**，是子类对父类抽象方法的完成实现

<font color=blue>**3. 抽象类的特征**</font>

- **有得：抽象类得到了<font color=red>拥有抽象方法</font>的能力。**

- **有失：抽象类失去了<font color=red>创建对象</font>的能力。**

<font color=blue>**4. 抽象类的细节**</font>

- 抽象类<font color=red>**不能创建对象**</font>。只能创建其非抽象子类的对象。

  > 理解：假设创建了抽象类的对象，调用抽象的方法，而抽象方法没有具体的方法体，没有意义。

- 抽象类中，可以有构造方法，是供子类创建对象时，初始化父类成员使用的。

  > 理解：子类的构造方法中，有默认的super()，需要访问父类构造方法。

- 抽象类中，不一定包含抽象方法，但是有抽象方法的类必定是抽象类。

  > 理解：未包含抽象方法的抽象类，目的是不想让调用者创建该类对象，通常用于某些特殊的类结构设计。

- 抽象类的子类，必须重写抽象父类中<font color=red>**所有的**抽象方法</font>，否则子类也必须定义成抽象类，编译无法通过而报错。

  > 理解：假设不重写所有抽象方法，则类中可能包含抽象方法。那么创建对象后，调用抽象方法，无意义。

- 抽象类存在的意义是为了被子类继承。抽象类可以<font color=red>**强制让子类，一定要按照规定的格式进行重写**</font>



### 3.8 接口

**接口是更加彻底的抽象，JDK7之前，包括JDK7，接口中全部是抽象方法。<font color=red>接口同样是不能创建对象的</font>**

#### 3.8.1 接口思想

<font color=blue>**1. 接口的定义**</font>

接口名称：**首字母大写，满足“驼峰模式”**

```java
interface 接口名称{
    // 抽象方法
}
```

<font color=blue>**2. 接口中成员的特点**</font>

- **成员变量**
  - 只能是常量
  - 默认修饰符：<font color=red>**public static final，大写**</font>
- **构造方法**：没有
- **成员方法**
  - 只能是抽象方法(接口中的抽象方法默认会自动加上public abstract修饰程序员**无需自己手写**)
  - 默认修饰符：<font color=red>**public abstract**</font>

- **版本更新**
  - 在JDK7以前：接口中只能定义抽象方法
  - JDK8的新特性：接口中可以定义有方法体的方法(默认、静态)
  - JDK9的新特性：接口中可以定义私有方法  


```java
public interface InterF {
    //    public abstract void run();
    void run();

    // public static final int AGE = 12 ;
    int AGE  = 12; //常量
}
```

<font color=blue>**3. 基本的实现**</font>

类与接口的关系为实现关系，即<font color=red>**类实现接口**</font>，该类可以称为接口的实现类，也可以称为接口的子类。实现的动作类似继承，格式相仿，只是关键字不同，实现使用 <font color=red>**implements**</font> 关键字。

实现接口的格式：

```java
class 类名 implements 接口1,接口2,接口3...{
}
class 类名 extends 父类 implements 接口1，接口2,...{
}
```

==注意==：

1. **必须重写实现的全部接口中所有抽象方法**。
2. 如果一个类实现了接口，但是没有重写完全部接口的全部抽象方法，这个类也必须定义成**抽象类**。

<font color=blue>**4. 接口的意义**</font>

接口体现的是一种规范，接口对实现类是一种强制性的约束，要么全部完成接口申明的功能，要么自己也定义成抽象类。这正是一种<font color=red>**强制性的规范**</font>。

#### 3.8.2 接口与接口的多继承

接口与接口之间是可以多继承的：也就是一个接口可以同时继承多个接口。一定要注意：

- **类与接口是实现关系**
- **接口与接口是继承关系**

接口继承接口就是把其他接口的抽象方法与本接口进行了<font color=red>**合并**</font>。

```java 
public interface Abc {
    void go();
    void test();
}
/** 法律规范：接口*/
public interface Law {
    void rule();
    void test();
}
public interface SportMan extends Law , Abc {
    void run();
}
```

<font color=blue>**接口的细节：**</font>

1. 当两个接口中存在相同抽象方法的时候，该怎么办？

> 只要重写一次即可。此时重写的方法，既表示重写1接口的，也表示重写2接口的。

2. 实现类能不能继承A类的时候，同时实现其他接口呢？

> 继承的父类，就好比是亲爸爸一样
> 实现的接口，就好比是干爹一样
> 可以继承一个类的同时，再实现多个接口，只不过，要把接口里面所有的抽象方法，全部实现。

3. 实现类能不能继承一个抽象类的时候，同时实现其他接口呢？

> 实现类可以继承一个抽象类的同时，再实现其他多个接口，只不过要把里面**所有的抽象方法全部重写**。

4. 实现类Zi，实现了一个接口，还继承了一个Fu类。假设在接口中有一个方法，父类中也有一个相同的方法。子类如何操作呢？

> 处理办法一：如果父类中的方法体，能满足当前业务的需求，在子类中可以不用重写。
> 处理办法二：如果父类中的方法体，不能满足当前业务的需求，需要在子类中重写。

5. ==**如果一个接口中，有10个抽象方法，但是我在实现类中，只需要用其中一个，该怎么办?**==

> 可以在接口跟实现类中间，新建一个中间类（**适配器类**）
> 让这个适配器类去实现接口，对接口里面的所有的方法做空重写。
> 让子类继承这个适配器类，想要用到哪个方法，就重写哪个方法。
> 因为中间类没有什么实际的意义，所以一般会把中间类定义为**抽象的**，不让外界创建对象

#### 3.8.3 JDK升级下的接口

<font color=blue>**1. JDK8之后接口中新增默认方法**</font>

- 允许在接口中定义默认方法，需要使用<font color=red>**关键字default**</font>修饰

  <font color=red>**作用：解决接口升级问题**</font>

- 接口中默认方法的**定义格式**：

  ```java
  public default 返回值类型 方法名(参数列表){}
  ```

- 接口中默认方法的**注意事项：**

  - 默认方法不是抽象方法，所以不强制重写，但若要重写，<font color=red>**重写的时候去掉default关键字**</font>
  - public可以省略，但**default不能省略**
  - 若实现了多个接口，多个接口中存在相同名字的默认方法，子类必须对该方法进行重写

```java
public default void show(){
    System.out.println("接口中的默认方法");
}
```

<font color=blue>**2. JDK8之后接口中新增静态方法**</font>

- 允许在接口中定义静态方法，需要用**static修饰**

- 接口中静态方法的定义格式：

  ```java
  public static 返回值类型 方法名(参数列表){}
  ```

- 接口中静态方法的**注意事项**：

  - 静态方法**只能通过接口名调用，不能通过实现类名或对象名调用**

    ```java
    Inter.show();  
    ```

  - public可以省略，static不能省略

<font color=blue>**3. JDK9之后接口中新增方法**</font>

私有方法的定义格式：

```java
private 返回值类型 方法名(参数列表){}
private static 返回值类型 方法名(参数列表){}
```

#### 3.8.4 适配器设计

**接口多态**：当一个方法的参数是接口，可传递接口所有实现类的对象

**设计模式**：一套被反复使用、多数人知晓、经过分类编目的、代码设计经验的总结。使用设计模式为了可重复用代码、让代码更容易被理解、保证代码可靠性、程序的重用性。简单理解：**设计模式是各种套路**

**适配器设计模式**：解决接口与接口实现类之间的矛盾

- 当一个接口中抽象方法过多，但是**只要使用其中一部分的时候，就可以使用适配器设计模式**
- 书写步骤
  - 编写中间类<font color=red>**xxxAdapter**</font>，实现对应的接口
  - 对接口中的抽象方法进行空实现
  - 让真正的实现类继承中间类，并重写需要用的方法

```java
public abstract class InterAdapter implements Inter{
    //使用适配器类实现接口，对接口中所有方法进行空实现
}
```

```java
public class InterImp1 extends InterAdapter{
    //此类只需要继承适配器，需要用到哪个方法就重写哪个方法就行
}
```



### 3.9 内部类

<font color=blue>**1. 类的五大成员**</font>

属性、方法、构造方法、代码块、内部类

<font color=blue>**2. 什么时候使用内部类？**</font>

一个事物内部还有一个独立的事物，内部的事物脱离外部事物无法独立使用

<font color=blue>**3. 内部类的分类**</font>

- **成员内部内**，类定义在了**成员**位置 (类中方法外称为成员位置，无static修饰的内部类)
- **静态内部类**，类定义在了**成员**位置 (类中方法外称为成员位置，**有static**修饰的内部类)
- **局部内部类**，类定义在**方法内**
- **匿名内部类**，**没有名字的内部类**，可以在方法中，也可以在类中方法外

<font color=blue>**4. 内部类的访问特点**</font>

- 内部类<font color=red>**可以直接访问**</font>外部类的成员，包括私有
- 外部类要访问内部类的成员，**必须创建对象**

#### 3.9.1 成员内部类

<font color=blue>**1. 特点**</font>

**写在成员位置，属于外部类的成员**

```java
public class Car{ //外部类
    String carName;
    int carAge;
    class Engine{ //成员内部类
        String engineName;
        int engineAge;
    }
}
```

- 无static修饰的内部类，属于外部类对象的
- 宿主：外部类对象

<font color=blue>**2. 使用格式**</font>

```java
 外部类.内部类。 // 访问内部类的类型都是用 外部类.内部类
```

<font color=blue>**3. 获取成员内部类对象**</font>

**方式一：外部直接创建成员内部类的对象**

```java
外部类.内部类 变量 = new 外部类（）.new 内部类（）;
Outer.Inner oi = new Outer().new Inner();
```

**方式二：在外部类中定义一个方法提供内部类的对象 --- <font color=red>用private修饰内部类时使用</font>** 

```java
public class Outer {
    String name;
    private class Inner{
        static int a = 10;
    }
    public Inner getInstance(){
        return new Inner();
    }
}
public class Test {
    public static void main(String[] args) {
        Outer o = new Outer();
        System.out.println(o.getInstance());
    }
}
```

<font color=blue>**4. 成员内部类细节**</font>

①编写成员内部类的注意点：

- 成员内部类可以被一些修饰符所修饰，比如： private，默认，protected，public，static等

- 在成员内部类里面，JDK16之前不能定义静态变量，JDK16开始才可以定义静态变量

- 创建内部类对象时，对象中有一个隐含的**Outer.this记录外部类对象的地址值**

②详解：

- 内部类被**private**修饰，外界无法直接获取内部类的对象，**只能通过方式二**获取内部类的对象

- 被其他权限修饰符修饰的内部类一般用方式一直接获取内部类的对象

- 内部类被static修饰是成员内部类中的特殊情况，叫做静态内部类

- 内部类如果想要访问外部类的成员变量，外部类的变量**必须用final**修饰，JDK8以前必须手动写final，JDK8之后不需要手动写，JDK默认加上

###### 面试题

==请在?地方加上相应代码,以达到输出的内容==

注意：内部类访问外部类对象的格式是：**外部类名.this**

```java
public class Test {
    public static void main(String[] args) {
        Outer.inner oi = new Outer().new inner();
        oi.method();
    }
}

class Outer {	
    private int a = 30;
    class inner {
        private int a = 20;
        public void method() {
            int a = 10;
            System.out.println(???);	// 10           答案：a
            System.out.println(???);	// 20	        答案：this.a
            System.out.println(???);	// 30	        答案：Outer.this.a
        }
    }
}
```

<font color=blue>**5. 成员内部类内存图**</font>

![内部类内存图](javaBasis_assets\21.png)

#### 3.9.2 静态内部类

<font color=blue>**1. 特点**</font>

* 静态内部类是**一种特殊的成员内部类，有static修饰**，属于外部类本身的。

- 静态内部类与其他类的用法完全一样。只是访问的时候需要加上外部类.内部类。

- **拓展1**:静态内部类可以**直接访问外部类的静态成员**。

- **拓展2**:静态内部类不可以直接访问外部类的**非静态**成员，如果要访问需要**创建外部类的对象**。

- **拓展3**:静态内部类中没有银行的Outer.this。

<font color=blue>**2. 使用格式**</font>

```
外部类.内部类。
```

<font color=blue>**3. 创建格式**</font>

```java
外部类.内部类  变量 = new  外部类.内部类构造器;
```

<font color=blue>**4. 调用方法的格式**</font>

* 调用**非静态方法**的格式：先创建对象，用对象调用
* 调用**静态方法**的格式：<font color=red>**外部类名.内部类名.方法名();**</font>

```java
class Outer{
    private static  String sc_name = "黑马程序";
    public static class Inner{
        private String name;
        public Inner(String name) {
            this.name = name;
        }
        public void showName(){
            System.out.println(this.name);
            // 静态内部类可以直接访问外部类的静态成员
            System.out.println(sc_name);
        }
    }
}
public class InnerClassDemo {
    public static void main(String[] args) {
        Outer.Inner in  = new Outer.Inner("张三");
        in.showName();
    }
}
```

#### 3.9.3 局部内部类

- 定义在**方法中**的类，类似于**方法中的局部变量**

  - 表示能够修饰局部变量的，便可以修饰局部内部类，不能修饰局部变量的则不能修饰局部内部类

  - 例如可以用final修饰局部变量

    ```java
    public class Outer{
        public void show(){
            final int a = 10;
        	final class Inner{
        	}
        }
    }
    ```

- **外界无法直接使用**，需要在方法内部创建对象并使用

- 该类可以直接访问外部类的成员，也可以访问方法内的局部变量

```java
class 外部类名 {
	数据类型 变量名;
	修饰符 返回值类型 方法名(参数列表) {
		class 内部类 {
			// 成员变量
			// 成员方法
		}
	}
} 
```

#### 3.9.4 匿名内部类

**匿名内部类** ：内部类的简化写法。是一个隐含了名字的内部类，可以写在成员位置/局部位置。**开发中最常用到**

<font color=blue>**1. 格式**</font>

```java
new 类名或者接口名() {
     重写方法;
};
```

匿名内部类包含了：

* 继承/实现

* 方法重写
* **创建对象**

所以从语法上来讲，这个整体其实是<font color=red>**匿名内部类对象**</font>

```java
public interface Swim{
    public abstract void swim();
}
new Swim(){  //1.Swim实现Swim接口   //3.new对象(匿名内部类的对象)
    @Override
    public void swim(){ //2.重写swim方法
        System.out.println("重写的方法");
    }
};
```

<font color=blue>**2. 什么时候使用匿名内部类？**</font>

**如果希望定义一个只要使用一次的类，就可考虑使用匿名内部类。匿名内部类的本质作用是为了简化代码** 

之前使用接口时，似乎得做如下几步操作：

​	①定义子类

​	②重写接口中的方法

​	③创建子类对象

​	④调用重写后的方法

目的最终只是为了<font color=red>**调用方法**</font>，那么能不能简化一下，把以上四步合成一步呢？匿名内部类就是做这样的**快捷方式**

<font color=blue>**3. 匿名内部类前提和格式**</font>

匿名内部类必须**继承一个父类**或者**实现一个父接口**

```java
new 父类名或者接口名(){};
```

<font color=blue>**4. 使用方式**</font>

- 使用匿名内部类实现仅使用一次的对象创建
- 使用匿名内部类实现接口多态
- 使用匿名内部类调用自身方法

```java
interface Swim {
    public abstract void swimming();
}

public class Demo {
    public static void main(String[] args) {
        // 使用匿名内部类
		new Swim() {
			@Override
			public void swimming() {
				System.out.println("自由泳...");
			}
		}.swimming(); //调用方法

        // 接口 变量 = new 实现类(); // 多态,走子类的重写方法
        // 实现了接口多态
        Swim s2 = new Swim() {
            @Override
            public void swimming() {
                System.out.println("蛙泳...");
            }
        };
        s2.swimming();
        s2.swimming();
    }
}
```

<font color=blue>**5. 匿名内部类的特点**</font>

- 定义一个没有名字的内部类

- 这个类实现了父类，或者父类接口

- 匿名内部类会创建这个没有名字的类的对象

<font color=blue>**6. 匿名内部类的使用场景**</font>

通常在方法的形式参数是接口或者抽象类时，也可以将匿名内部类作为**参数传递**。代码如下：

```java
interface Swim {
    public abstract void swimming();
}

public class Demo {
    public static void main(String[] args) {
        // 1. 匿名内部类使用场景:作为方法参数传递
        Swim s3 = new Swim() {
            @Override
            public void swimming() {
                System.out.println("蝶泳...");
            }
        };
        // 传入匿名内部类
        goSwimming(s3);

        // 2. 完美方案: 一步到位
        goSwimming(new Swim() {
            public void swimming() {
                System.out.println("大学生, 蛙泳...");
            }
        });
    }

    // 定义一个方法,模拟请一些人去游泳
    public static void goSwimming(Swim s) {
        s.swimming();
    }
}
```

<font color=blue>**7. 补充**</font>

- 在项目中右击点击Explorer，找到out文件夹(存放所有字节码文件，即编译后的class文件)

<img src="javaBasis_assets\34.png" alt="image-20240630142920804" style="zoom:50%;" />

- 发现匿名内部类是有名字的，例如文件为Test.class，运行后匿名内部类会生成Test$1.class
- 输入```javap Test$1.class```进行反编译，会发现其便是匿名内部类

---





# Java常用API



## 1 API

<font color=blue>**1. 什么是API？**</font>

- Application Programming Interface，应用程序接口
- 简单理解：别人写好的东西，不需要自己编写，直接使用即可

<font color=blue>**2. Java API是什么？**</font>

JDK 中提供的各种功能的 Java类，这些类将底层的实现封装了起来，不需要关心这些类是如何实现的，只需要学习这些类如何使用即可，可以通过帮助文档来学习这些API如何使用

<font color=blue>**3. 如何使用API帮助文档？**</font>

- 打开帮助文档

![01](javaBasis_assets\22.png)

- 点击显示，找到索引选项卡中的输入框

![02](javaBasis_assets\23.png)

- 在输入框中输入Random

![03](javaBasis_assets\24.png)

- 看类在哪个包下

![04](javaBasis_assets\25.png)

- 看类的描述

![05](javaBasis_assets\26.png)

- 看构造方法

![06](javaBasis_assets\27.png)

- 看成员方法

![07](javaBasis_assets\28.png)

---



## 2 字符串

### 2.1 String

String 类在 java.lang 包下，所以使用的时候不需要导包！

- 字符串不可变，它们的值在创建后**不能被更改**
- 虽然 String 的值是不可变的，但是它们可以被共享
- 字符串效果上相当于<font color=red>**字符数组( char[] )**</font>，但是底层原理是<font color=red>**字节数组( byte[] )**</font>

#### 2.1.1 基本使用

<font color=blue>**1. 常用的构造方法**</font>

| 方法名                      | 说明                                      |
| --------------------------- | ----------------------------------------- |
| public   String()           | 创建一个空白字符串对象，不含有任何内容    |
| public   String(char[] chs) | 根据字符数组的内容，来创建字符串对象      |
| public   String(byte[] bys) | 根据字节数组的内容，来创建字符串对象      |
| String s =   “abc”;         | 直接赋值的方式创建字符串对象，内容就是abc |

<font color=blue>**2. 常用方法**</font>

| 方法名                            | 说明                                     |
| --------------------------------- | ---------------------------------------- |
| ==**s.indexof('a')**==            | 返回字符a所在字符串中的索引              |
| ==**s.charAt(1)**==               | 返回索引处字符串对应的字符               |
| ==**s.replace("TMD","\*\*\*")**== | 替代指定字符                             |
| ==**s.subString(a,b)**==          | 截取字符串[a,b)                          |
| ==**s.subString(a)**==            | 去掉a之前的字符，得到包含a位置及以后字符 |
| **s.trim()**                      | 去除字符串两边空白                       |
| **s.toLowerCase()/UpperCase**     | 将字符串转成小写/大写                    |
| **s.length()**                    | 字符串长度                               |
| ==**s.equals(b)**==               | 判定是否相等                             |

<font color=blue>**3. 示例代码**</font>

```java
public class StringDemo {
    public static void main(String[] args) {
        //public String()：创建一个空白字符串对象，不含有任何内容
        String s1 = new String();
        System.out.println("s1:" + s1);

        //public String(char[] chs)：根据字符数组的内容，来创建字符串对象
        char[] chs = {'a', 'b', 'c'};
        String s2 = new String(chs);
        System.out.println("s2:" + s2);

        //public String(byte[] bys)：根据字节数组的内容，来创建字符串对象
        byte[] bys = {97, 98, 99};
        String s3 = new String(bys);
        System.out.println("s3:" + s3);

        //String s = “abc”;	直接赋值的方式创建字符串对象，内容就是abc
        String s4 = "abc";
        System.out.println("s4:" + s4);
    }
}
```

<font color=blue>**4. 创建字符串对象两种方式的区别**</font>

- 构造方法创建

  通过 new 创建的字符串对象，<font color=red>**每一次 new 都会申请一个内存空间**</font>，**虽然内容相同，但是地址值不同**


  - 直接赋值创建

    以“”方式给出的字符串，只要字符序列相同(顺序和大小写)，无论在程序代码中出现几次，<font color=red>**JVM 都只会建立一个 String 对象**</font>，并在字符串池中维护

    - 不存在：创建新的
    - 存在：复用
    - 因此，采用直接赋值的方法可以节约内存，**推荐使用**

#### 2.1.2 ==与equals

<font color=blue>**1. ==**</font>

- 比较基本数据类型：比较的是具体的值

- 比较引用数据类型：比较的是<font color=red>**对象地址值**</font>

  ```java
  String s1 = "abc";
  String s2 = "abc";
  System.out.println(s1==s2);    //true
  
  String s1 = new String("abc"); //记录的是堆里的地址值
  String s2 = "abc";             //记录的是串池中的地址值
  System.out.println(s1==s2);    //false
  ```

<font color=blue>**2. equals**</font>

比较字符串里面的内容

```java
public boolean equals(String s)           区分大小写比较
public boolean equalsIgnoreCase(String s) 忽略大小写的比较    
```

```java
//构造方法的方式得到对象
char[] chs = {'a', 'b', 'c'};
String s1 = new String(chs);
String s2 = new String(chs);
//直接赋值的方式得到对象
String s3 = "abc";
String s4 = "abc";
//键盘录入方式得到对象
Scanner sc = new Scanner(System.in);
System.out.println("请输入一个字符串");
String s5 = sc.next();  //abc，new出来的

//比较字符串对象地址是否相同
System.out.println(s1 == s2); //false
System.out.println(s1 == s3); //false
System.out.println(s3 == s4); //true
System.out.println(s3 == s5); //false

//比较字符串内容是否相同
System.out.println(s1.equals(s2));
System.out.println(s1.equals(s3));
System.out.println(s3.equals(s4));
```

###### 练习1：遍历字符串

```java
for (int i = 0; i < str.length(); i++) {
    char c = str.charAt(i);
    System.out.println(c);
}
```

###### 练习2：字符串反转

键盘录入 abc，输出结果 cba

```java
//fori :正着遍历  forr：倒着遍历
String s = "";
for (int i = str.length() - 1; i >= 0; i--) {
    s = s + str.charAt(i);
}
return s;
```

###### 练习3：金额转换

​	把2135变成：零佰零拾零万贰仟壹佰叁拾伍元 

​	把789变成：零佰零拾零万零仟柒佰捌拾玖元

思路：**查表法**，将数据与索引产生一一对应关系，即数字->大写符号

<img src="javaBasis_assets\29.png" alt="image-20240627185536460" style="zoom:50%;" />

```java
import java.util.Scanner;

public class StringDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int money;
        while (true) {
            System.out.println("请录入一个金额");
            money = sc.nextInt();
            if (money >= 0 && money <= 9999999) {
                break;
            } else {
                System.out.println("金额无效");
            }
        }
        String moneyStr = "";

        //得到money里面的每一位数字,再转成中文
        while (true) {//2135
            //从右往左获取数据，因为右侧是数据的个位
            int ge = money % 10;
            String capitalNumber = getCapitalNumber(ge);
            //把转换之后的大写拼接到moneyStr当中
            moneyStr = capitalNumber + moneyStr;
            //第一次循环 ： "伍" + "" = "伍"
            //第二次循环 ： "叁" + "伍" = "叁伍"
            //去掉刚刚获取的数据
            money = money / 10;
            //如果数字上的每一位全部获取到了，那么money记录的就是0，此时循环结束
            if (money == 0) {
                break;
            }
        }

        //在前面补0，补齐7位
        int count = 7 - moneyStr.length();
        for (int i = 0; i < count; i++) {
            moneyStr = "零" + moneyStr;
        }
        System.out.println(moneyStr);//零零零贰壹叁伍

        //插入单位
        //定义一个数组表示单位
        String[] arr = {"佰","拾","万","仟","佰","拾","元"};
        //               零    零   零   贰   壹   叁   伍

        //遍历moneyStr，依次得到 零    零   零   贰   壹   叁   伍
        //然后把arr的单位插入进去

        String result = "";
        for (int i = 0; i < moneyStr.length(); i++) {
            char c = moneyStr.charAt(i);
            //把大写数字和单位拼接到result当中
            result = result + c + arr[i];
        }
        //打印最终结果
        System.out.println(result);
    }

    //定义一个方法把数字变成大写的中文
    //1 -- 壹
    public static String getCapitalNumber(int number) {
        //定义数组，让数字跟大写的中文产生一个对应关系
        String[] arr = {"零", "壹", "贰", "叁", "肆", "伍", "陆", "柒", "捌", "玖"};
        //返回结果
        return arr[number];
    }
}
```

###### 练习4：统计关键词

现有如下文本："Java语言是面向对象的，Java语言是健壮的，Java语言是安全的，Java是高性能的，Java语言是跨平台的"。请编写程序，统计该文本中"Java"一词出现的次数。

```java
public class Test {
    public static void main(String[] args) {
        String str = "Java语言是面向对象的，Java语言是健壮的，Java语言是安全的，Java是高性能的，Java语言是跨平台的";
        String tar = "Java";
        System.out.println(search(str, tar));
    }

    // 替换之后求长度差
    public static int search(String str, String tar) {
        String newStr = str.replace(tar, "");
        int count = (str.length() - newStr.length()) / tar.length();
        return count;
    }
}
```

### 2.2 StringBuilder

StringBuilder 可以看成是一个容器，创建之后里面的内容是<font color=red>**可变的**</font>

- 使用：在<font color=red>**拼接字符串**</font>和<font color=red>**反转字符串**</font>的时候会使用到
- 作用：提高字符串的操作效率，帮助操作字符串

#### 2.2.1 基本使用

<font color=blue>**1. 构造方法**</font>

```java
public StringBuilder()            //创建一个空白可变字符串对象，不含任何内容
public StringBuilder(String str)  //根据字符串内容，创建可变字符串对象    
```

<font color=blue>**2. 常用方法**</font>

| ==append(任意类型)== | 添加数据，并返回对象本身StringBuilder |
| -------------------- | ------------------------------------- |
| **==reverse()==**    | 反转容器中的内容                      |
| ==**length()**==     | 返回长度(字符出现的个数)              |
| ==**toString()**==   | 把StringBuilder转换为String           |

```java
//创建对象
StringBuilder sb = new StringBuilder("abc");

//添加元素
sb.append(1);
//反转
sb.reverse();
//获取长度
int len = sb.length();
System.out.println(len);

//因为StringBuilder是Java已经写好的类，java在底层对他做了一些特殊处理
//打印对象不是地址值而是属性值
System.out.println(sb);
```

#### 2.2.2 链式编程

**链式编程**：在调用一个方法时，不需要用变量接收其结果，可以继续调用其他方法

```java
int len = getString().subString(1).replace("A","Q").length();//转换为String后可用其方法
```

```java
StringBuilder sb = new StringBuilder();

sb.append("aaa").append("bbb").append("ccc").append("ddd");
System.out.println(sb);//aaabbbcccddd

String str = sb.toString();
System.out.println(str);//aaabbbcccddd
```

###### 练习1：对称字符串 

==需求：键盘接受一个字符串，程序判断出该字符串是否是对称字符串，并在控制台打印是或不是==

  	对称字符串：123321、111
  	非对称字符串：123123

```java
//反转键盘录入的字符串
String result = new StringBuilder().append(str).reverse().toString();

//比较
if(str.equals(result)){
    System.out.println("当前字符串是对称字符串");
}else{
    System.out.println("当前字符串不是对称字符串");
}
```

###### 练习2：拼接字符串 

==需求：定义方法，把 int 数组中的数据按照指定格式拼接成一个字符串返回。调用该方法，在控制台输出结果。==

例如：数组为int[] arr = {1,2,3}; 执行方法后的输出结果为：[1, 2, 3]

```java
StringBuilder sb = new StringBuilder();
sb.append("[");
for (int i = 0; i < arr.length; i++) {
    if(i == arr.length - 1){
        sb.append(arr[i]);
    }else{
        sb.append(arr[i]).append(", ");
    }
}
sb.append("]");
return sb.toString();
```

### 2.3 StringJoiner

* StringJoiner跟StringBuilder一样，也可以看成是一个容器，创建之后里面的内容是**可变的**
* 作用：提高字符串的操作效率，而且代码编写特别简洁，但是目前市场上很少有人用  
* JDK8出现的

<font color=blue>**1. 构造方法**</font>

```java
public StringJoiner(间隔符号) 
public StringJoiner(间隔符号,开始符号,结束符号) 
```

<font color=blue>**2. 成员方法**</font>

```java
public StringJoiner add(添加的内容)  //添加数据，并返回对象本身
public int length()                //返回长度(字符出现的个数)
public String toString()           //返回一个字符串(该字符串就是拼接之后的结果)        
```

<font color=blue>**3. 代码示例**</font>

```java
//1.创建一个对象，并指定中间的间隔符号
StringJoiner sj = new StringJoiner("---");
//2.添加元素
sj.add("aaa").add("bbb").add("ccc");
//3.打印结果
System.out.println(sj);//aaa---bbb---ccc
```

```java
StringJoiner sj = new StringJoiner(", ","[","]");

sj.add("aaa").add("bbb").add("ccc");
int len = sj.length();
System.out.println(len);

System.out.println(sj);
```

### 2.4 字符串相关的底层逻辑

<font color=blue>**1. 字符串存储的内存原理**</font>

- **直接赋值**会**复用**字符串常量池中的
- **new**出来不会复用，而是**开辟**一个新空间

<font color=blue>**2. ==号比较的到底是什么**</font>

- 基本数据类型比较数据值
- 引用数据类型比较**地址值**

<img src="javaBasis_assets\30.png" alt="image-20240627214029502" style="zoom:50%;" />

<font color=blue>**3. 字符串拼接的底层原理**</font>

- 拼接时没有变量：编译之后就是拼接之后的结果，会复用串池中的字符串

![image-20240627212621669](javaBasis_assets\31.png)

- 拼接时有变量：每一行拼接的代码，都会在内存中**创建新的字符串**，浪费内存
  - JDK8以前会使用StringBuilder---非常浪费性能
  - Jdk8之后先预估，再分配

![image-20240627213226521](javaBasis_assets\32.png)

<font color=blue>**4. StringBuilder提高效率原理图**</font>

StringBuilder是一个内容可变的容器，所有要拼接的内容都会放在StringBuilder中，不会创建许多无用的空间，节约内存

**StringBuilder源码分析**

![image-20240627214447791](javaBasis_assets\33.png)

![image-20240627214820780](C:/Users/周歆怡/Desktop/周记/JavaBasis/assets/14.png)

- 默认会创建一个长度为16的字节数组
- 添加的内容长度小于16会直接存
- 添加的内容大于16会扩容(原来的容量*2+2)

---



## 3 Math类

Math类所在包为java.lang包，因此在使用的时候不需要进行导包

Math类被final修饰了，因此该类是**不能被继承**的

Math类包含执行基本数字运算的方法，可以使用Math类完成基本的**数学运算**

<font color="blue" size="3">**1. 常见方法**</font>

| 方法                    | 含义                                               |
| ----------------------- | -------------------------------------------------- |
| abs(int a) / absExact() | 返回参数绝对值 / 数值太大时超int范围返回参数绝对值 |
| ceil(double a)          | **向上取整**，返回>=参数的最小整数                 |
| floor(double a)         | **向下取整**，<=参数的最大整数                     |
| round(float a)          | 四舍五入最接近参数的int值                          |
| max(int a,int b)        | 两个int中的最大值                                  |
| min(int a,int b)        | 两个int中的最小值                                  |
| pow(double a,double b)  | a的b次幂                                           |
| random()                | <font color=red>**[0.0, 1.0)**</font>的随机值      |
| cbrt(double)            | 返回double的立方根                                 |
| **sqrt(double)**        | 返回double的**平方根**                             |

 在API文档中没有体现可用的构造方法，因此就**不能直接通过new关键字去创建Math类的对象**。同时发现Math类中的方法都是静态的，因此在使用的时候可以直接通过**类名去调用**。

###### 练习1：判断质数

优化思想：不需要全部遍历，以平方根为依据

```java
public class MathDemo2 {
    public static void main(String[] args) {
        System.out.println(isPrime(997));
    }

    public static boolean isPrime(int number) {
        int count = 0;
        for (int i = 2; i <= Math.sqrt(number); i++) { //可以更改循环的结束条件
            count++;
            if (number % i == 0) {
                return false;
            }
        }
        System.out.println(count);
        return true;
    }
}
```

###### 练习2：自幂数

一个n位自然数等于自身各个数位上数字的n次幂之和

​	举例1：三位数  1^3 + 5^3 + 3^3 = 153  

​	举例2：四位数  1^4 + 6^4 + 3^4 + 4^3 = 1634

如果自幂数是：

* 一位自幂数，也叫做：独身数
* 三位自幂数：水仙花数  四位自幂数：四叶玫瑰数
* 五位自幂数：五角星数  六位自幂数：六合数
* 七位自幂数：北斗七星数  八位自幂数：八仙数
* 九位自幂数：九九重阳数  十位自幂数：十全十美数

​	要求1：统计一共有多少个水仙花数。

​	要求2：证明没有两位的自幂数。

​	要求3：分别统计有多少个四叶玫瑰数和五角星数。（答案：都是3个）

```java
//水仙花数:100 ~ 999
int count = 0;
//得到每一个三位数
for (int i = 100; i <= 999; i++) {
    //个位 十位 百位
    int ge = i % 10;
    int shi = i / 10 % 10;
    int bai = i / 100 % 10;
    //判断:每一位的三次方之和 跟本身 进行比较。
    double sum = Math.pow(ge, 3) + Math.pow(shi, 3) + Math.pow(bai, 3);
    if (sum == i) {
        count++;
        System.out.println(count);
    }
}
```

---



## 4 System类

- System类所在包为java.lang包，因此在使用的时候不需要进行导包

- System类被final修饰了，因此该类是**不能被继承**的

- System包含了**系统操作**的一些常用的方法。比如获取当前时间所对应的毫秒值，再比如终止当前JVM等等

- 在API文档中没有体现System可用的构造方法，因此**不能直接**通过new关键字去创建System类的对象

- System类中的方法都是静态的，因此在使用的时候可以直接通过**类名去调用**（Nested Class Summary内部类或者内部接口的描述）

<font color="blue">**1. currentTimeMillis**</font>

获取**当前时间所对应的毫秒值**（当前时间为0时区所对应的时间即就是英国格林尼治天文台旧址所在位置）

计算机中的时间原点：1970年1月1日 00:00:00，我们国家是08:00:00

```java
// 获取当前时间所对应的毫秒值
long millis = System.currentTimeMillis();
```

获取到当前时间的毫秒值的意义：常常来需要**统计某一段代码的执行时间**。此时就可以在执行这段代码之前获取一次时间，在执行完毕以后再次获取一次系统时间，然后计算两个时间的差值，这个差值就是这段代码执行完毕以后所需要的时间。

```java
long start = System.currentTimeMillis();
... 执行方法
long end = System.currentTimeMillis();
//获取程序运行的总时间
System.out.println(end - start);   
```

<font color="blue">**2. exit**</font>

**终止当前正在运行的Java虚拟机**，0表示正常退出，非零表示异常退出

```java
System.out.println("程序开始执行了.....");
// 终止JVM
System.exit(0); 
System.out.println("程序终止了..........");  
```

运行程序进行测试，控制台输出结果如下：

```java
程序开始执行了.....
```

此时可以看到在控制台只输出了"程序开始了..."，由于JVM终止了，因此输出"程序终止了..."这段代码没有被执行

### arraycopy

<font color="blue">**3. arraycopy**</font>

**进行数值元素copy**

**1）方法参数说明：**

```java
// src: 	 源数组
// srcPos：  源数值的开始位置
// dest：    目标数组
// destPos： 目标数组开始位置
// length:   要复制的元素个数
public static native void arraycopy(Object src,  int  srcPos, Object dest, int destPos, int length); 
```

**2）数组元素拷贝：**

```java
// 定义源数组
int[] srcArray = {23 , 45 , 67 , 89 , 14 , 56 } ;
// 定义目标数组
int[] desArray = new int[10];

// 进行数组元素的copy: 把srcArray数组中从0索引开始的3个元素，从desArray数组中的1索引开始复制过去
System.arraycopy(srcArray , 0 , desArray , 1 , 3);
```

**3）数组元素的删除：**

```java
// 定义一个数组
int[] srcArray = {23 , 45 , 67 , 89 , 14 , 56 } ;
// 删除数组中第3个元素(67)：要删除67这个元素，只需要将67后面的其他元素依次向前进行移动即可
System.arraycopy(srcArray , 3 , srcArray , 2 , 3);
```

运行程序进行测试，控制台的输出结果如下所示：

```java
23, 45, 89, 14, 56, 56 
```

通过控制台输出结果我们可以看到此时多出了一个56元素，此时只需要**将最后一个位置设置为0即可**。如下所示：

```java
int[] srcArray = {23 , 45 , 67 , 89 , 14 , 56 } ;
System.arraycopy(srcArray , 3 , srcArray , 2 , 3);
// 将最后一个位置的元素设置为0
srcArray[srcArray.length - 1] = 0 ;
```

运行程序进行测试，控制台输出结果如下所示：

```java
23, 45, 89, 14, 56, 0
```

<font color="red" size="3">**arraycopy方法底层细节：**</font>

1.如果数据源数组和目的地数组都是基本数据类型，那么两者的类型**必须保持一致**，否则会报错

2.在拷贝的时候需要考虑数组的长度，如果超出范围也会报错，索引越界异常

3.如果数据源数组和目的地数组都是引用数据类型，那么**子类类型可以赋值给父类类型**

```java
public class SystemDemo3 {
    public static void main(String[] args) {
        Student s1 = new Student("zhangsan", 23);
        Student s2 = new Student("lisi", 24);
        Student s3 = new Student("wangwu", 25);

        Student[] arr1 = {s1, s2, s3};
        Person[] arr2 = new Person[3];
        System.arraycopy(arr1, 0, arr2, 0, 3); //引用数据类型拷贝的是对象的地址值

        for (int i = 0; i < arr2.length; i++) {
            Student stu = (Student) arr2[i];
            System.out.println(stu.getName() + "," + stu.getAge());
        }
    }
}
```

---



## 5 Runtime

Runtime表示Java中运行时对象，可以获取到**程序运行时涉及到的一些信息**

<font color="blue" size="3">**常见方法介绍**</font>

```java
public static Runtime getRuntime()		//当前系统的运行环境对象
public void exit(int status)			//停止虚拟机
public int availableProcessors()		//获得CPU的线程数/4或8
public long maxMemory()				    //JVM能从系统中获取总内存大小（单位byte）
public long totalMemory()				//JVM已经从系统中获取总内存大小（单位byte）
public long freeMemory()				//JVM剩余内存大小（单位byte）
public Process exec(String command) 	//运行cmd命令
```

```java
public class RunTimeDemo1 {
    public static void main(String[] args) throws IOException {   
        //1.获取Runtime的对象
        //Runtime r1 =Runtime.getRuntime();

        //2.exit 停止虚拟机
        //Runtime.getRuntime().exit(0);
        //System.out.println("看看我执行了吗?");

        //3.获得CPU的线程数
        System.out.println(Runtime.getRuntime().availableProcessors());//8
        //4.总内存大小,单位byte字节
        System.out.println(Runtime.getRuntime().maxMemory() / 1024 / 1024);//4064
        //5.已经获取的总内存大小,单位byte字节
        System.out.println(Runtime.getRuntime().totalMemory() / 1024 / 1024);//254
        //6.剩余内存大小
        System.out.println(Runtime.getRuntime().freeMemory() / 1024 / 1024);//251
        //7.运行cmd命令
        //shutdown :关机
        //加上参数才能执行
        //-s :默认在1分钟之后关机
        //-s -t 指定时间 : 指定关机时间
        //-a :取消关机操作
        //-r: 关机并重启
        Runtime.getRuntime().exec("shutdown -s -t 3600");
    }
}
```

---



## 6 Object

 Object类所在包是java.lang包。Object 是类层次结构的根，每个类都可以将 Object 作为父类。所有类都直接或者间接的继承自该类；换句话说，**该类所具备的方法，其他所有类都继承了**。

在Object类中提供了一个无参构造方法，但是一般情况下很少去主动的创建Object类的对象，调用其对应的方法。更多的是创建Object类的某个子类对象，然后通过子类对象调用Object类中的方法。

### 6.1 toString()

**返回该对象的<font color=red>字符串表示形式</font>(可以看做是对象的内存地址值)**

<font color=blue>**1. 获取对象的内存地址值**</font>

```java
public class ObjectDemo01 {
    public static void main(String[] args) {
        // 创建学生对象
        Student s1 = new Student("itheima" , "14") ;
        // 调用toString方法获取s1对象的字符串表现形式
        String result1 = s1.toString();
        // 输出结果
        System.out.println("s1对象的字符串表现形式为：" + result1);
    }
}
```

运行程序进行测试，控制台输出结果如下所示：

```java
s1对象的字符串表现形式为：com.itheima.api.system.demo04.Student@3f3afe78
```

为什么控制台输出的结果为：com.itheima.api.system.demo04.Student@3f3afe78； 此时可以查看一下Object类中toString方法的源码，如下所示：

```java
public String toString() {		// Object类中toString方法的源码定义
	return getClass().getName() + "@" + Integer.toHexString(hashCode());
}
```

- 其中getClass().getName()对应的结果就是：com.itheima.api.system.demo04.Student；Integer.toHexString(hashCode())对应的结果就是3f3afe78。

- 常常将"com.itheima.api.system.demo04.Student@3f3afe78"这一部分称之为**对象的内存地址值**。但是一般情况下获取对象的内存地址值没有太大的意义。

<font color=blue>**2. 获取对象的属性值**</font>

类中重写Object的toString方法。可以在IDEA中一键生成。

完成toString方法的重写，代码如下所示：

```java
@Override
public String toString() {
    return "Student{" +
        "name='" + name + '\'' +
        ", age='" + age + '\'' +
        '}';
}
```

把Student类中的成员变量进行了字符串的拼接。重写完毕以后，再次运行程序，控制台输出结果如下所示：

```java
s1对象的字符串表现形式为：Student{name='itheima', age='14'}
```

此时就可以清楚的查看Student的成员变量值，因此重写toString方法的意义就是以良好的格式，更方便的**展示对象中的属性值**

<font color=blue>**3. 直接输出对象名称，方便测试**</font>

```java
// 创建学生对象
Student s1 = new Student("itheima" , "14") ;

// 调用s1的toString方法，把结果进行输出
System.out.println(s1.toString());
```

### 6.2 equals()

比较两个**对象地址值是否相等**；true表示相同，false表示不相同

<font color=blue>**1. 比较对象地址值**</font>

```java
public class ObjectDemo02 {
    public static void main(String[] args) {
        // 创建两个学生对象
        Student s1 = new Student("itheima" , "14") ;
        Student s2 = new Student("itheima" , "14") ;
        // 比较两个对象是否相等
        System.out.println(s1 == s2);
    }
}
```

运行程序进行测试，控制台的输出结果如下所示：

```java
false
```

**"=="号**比较的是对象的地址值，而通过new关键字创建了两个对象，地址值是不相同的。因此比较结果就是false

尝试调用Object类中的**equals**方法进行比较

```java
// 调用equals方法比较两个对象是否相等
boolean result = s1.equals(s2);
// 输出结果
System.out.println(result);
```

运行程序进行测试，控制台的输出结果为：

```java
false
```

为什么结果还是false呢？可以查看一下Object类中equals方法的源码，如下所示：

```java
public boolean equals(Object obj) {		// Object类中的equals方法的源码
    return (this == obj);
}
```

通过源码可以发现**默认情况下equals方法比较的也是对象的地址值**。比较内存地址值一般情况下是没有意义的，希望比较的是对象的属性，如果两个对象的属性相同，认为就是同一个对象

<font color=blue>**2. 比较对象属性值**</font>

需要在类中重写Object类中的equals方法。

equals方法的重写，也可以使用idea开发工具完成，选择**equals() and hashCode()**方法

```java
@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (o == null || getClass() != o.getClass()) return false;
    Student student = (Student) o;
    return Objects.equals(name, student.name) && Objects.equals(age, student.age);	
    // 比较的是对象的name属性值和age属性值
}

@Override
public int hashCode() {
    return 0;
}
```

hashCode方法暂时使用不到，可以将hashCode方法删除。重写完毕以后运行程序进行测试

```java
true
```

此时equals方法比较的是对象的成员变量值，而s1和s2两个对象的成员变量值都是相同的。因此比较完毕以后的结果就是true。

###### 面试题

```java
String s = "abc";
StringBuilder sb = new StringBuilder("abc");

System.out.println(s.equals(sb));  //false
//因为equals方法是被s调用，而s是字符串，则equals要看String类中
//Ctrl+F12,查看String中equals的定义
//字符串中equals方法，先判断参数是否为字符串，若是字符串再比较内部属性
//若参数不是字符串，直接返回false

System.out.println(sb.equals(s));  //false
//因为equals方法是被sb调用，则equals要看StringBuilder类中
//StringBuilder中没有equals方法，默认继承Objects
//而Objects中equals方法比较的为地址值，所以结果为false
```

### 6.3 clone()

**对象克隆**： 把A对象的属性值完全拷贝给B对象，也叫对象拷贝,对象复制

**对象克隆的分类：**深克隆和浅克隆

<font color=blue>**1. 浅克隆**</font>

- **不管**对象内部的属性是基本数据类型还是引用数据类型，都**完全拷贝过来** 

- **基本**数据类型拷贝过来的是**具体的数据**，**引用**数据类型拷贝过来的是**地址值**

- Object类**默认的是浅克隆**

![浅克隆](javaBasis_assets\35.png)

<font color=blue>**2. 深克隆**</font>

<font color=red>**基本数据类型拷贝过来，字符串复用，引用数据类型会重新创建新的**</font>

![深克隆](javaBasis_assets\36.png)

代码实现：

```java
public class ObjectDemo {
    public static void main(String[] args) throws CloneNotSupportedException {
        //1.先创建一个对象
        int[] data = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 0};
        User u1 = new User(1, "zhangsan", "1234qwer", "girl11", data);

        //2.克隆对象
        //细节:方法在底层会帮我们创建一个对象,并把原对象中的数据拷贝过去
        //书写细节:
        //1.重写Object中的clone方法
        //2.让javabean类实现Cloneable接口
        //3.创建原对象并调用clone就可以了
        User u2 =(User)u1.clone();

        //验证一件事情：Object中的克隆是浅克隆
        //想要进行深克隆，就需要重写clone方法并修改里面的方法体
        int[] arr = u1.getData();
        arr[0] = 100;
        System.out.println(u1);
        System.out.println(u2);

        //以后一般会用第三方工具进行克隆
        //1.第三方写的代码导入到项目中
        //2.编写代码
        Gson gson =new Gson();
        //把对象变成一个字符串
        String s=gson.toJson(u1);
        //再把字符串变回对象就可以了
        User user =gson.fromJson(s, User.class);

        int[] arr=u1.getData();
        arr[0] = 100;
        System.out.println(user);
    }
}

import java.util.StringJoiner;
//Cloneable
//如果一个接口里面没有抽象方法
//表示当前的接口是一个标记性接口
//现在Cloneable表示一旦实现了，那么当前类的对象就可以被克隆
//如果没有实现，当前类的对象就不能克隆
public class User implements Cloneable {
    private int id;
    private String username;
    private String password;
    private String path;
    private int[] data;

    public User() {}
    public User(int id, String username, String password, String path, int[] data) {
        this.id = id;
        this.username = username;
        this.password = password;
        this.path = path;
        this.data = data;
    }

    public int getId() {return id;}
    public void setId(int id) {this.id = id;}
    public String getUsername() {return username;}
    public void setUsername(String username) {this.username = username;}
    public String getPassword() {return password;}
    public void setPassword(String password) {this.password = password;}
    public String getPath() {return path;}
    public void setPath(String path) {this.path = path;}
    public int[] getData() {return data;}
    public void setData(int[] data) {this.data = data;}
    public String toString() {
        return "角色编号为：" + id + "，用户名为：" + username + "密码为：" + password + ", 游戏图片为:" + path + ", 进度:" + arrToString();
    }
    public String arrToString() {
        StringJoiner sj = new StringJoiner(", ", "[", "]");
        for (int i = 0; i < data.length; i++) {
            sj.add(data[i] + "");
        }
        return sj.toString();
    }

    //若想要深克隆，则需要重写Clone()
    @Override
    protected Object clone() throws CloneNotSupportedException {
        //调用父类中的clone方法
        //相当于让Java帮我们克隆一个对象，并把克隆之后的对象返回出去。
        //先把被克隆对象中的数组获取出来
        int[] data = this.data;
        //创建新的数组
        int[] newData =new int[data.length];
        //拷贝数组中的数据
        for (int i = 0; i < data.length; i++) {
            newData[i] = data[i];
        }
        //调用父类中的方法克隆对象
            User u=(User)super.clone();
        //因为父类中的克隆方法是浅克隆，替换克隆出来对象中的数组地址值
        u.data =newData;
        return u;
    }
}
```

**以后的实际开发中若用到克隆，会用到第三方工具**

1.将第三方写的代码导入到项目中，在当前包下新建lib文件夹(与src同级)，ctrl-v点击ok

2.右键点击刚刚添加的第三方代码，选择Add as Library，点击再点击ok

3.编写代码

```java
//对添加的文件先新建对象
Gson gson = new Gson();
//把对象变成一个字符串
String s = gson.toJson(u1);
System.out.println(s);
//进行对象克隆，即将字符串再变为对象即可
gson.fromJson(s,User.class);
//打印对象
System.out.println(user);
```

---



## 7 Objects

Objects类所在包是在java.util包下，因此在使用的时候<font color=red>**需要进行导包**</font>

Objects类是被final修饰的，因此该类**不能被继承**

Objects类提供了一些**对象常见操作**的方法。比如判断对象是否相等，判断对象是否为null等等

Objects类中无无参构造方法，因此不能使用new关键字去创建Objects的对象。同时可以发现Objects类中所提供的方法都是静态的。因此可以通过**类名直接去调用**这些方法。

<font color="blue" size="3">**1. 常见方法介绍**</font>

```java
public static String toString(Object o) 					// 获取对象的字符串表现形式
public static boolean equals(Object a, Object b)			// 先做非空判断，再比较两个对象
public static boolean isNull(Object obj)					// 判断对象是否为null
public static boolean nonNull(Object obj)					// 判断对象是否不为null
```

Objects类中的常见方法如下所示：

```java
public static <T> T requireNonNull(T obj)					// 检查对象是否不为null,如果为null直接抛出异常；如果不是null返回该对象；
public static <T> T requireNonNullElse(T obj, T defaultObj) // 检查对象是否不为null，如果不为null，返回该对象；如果为null返回defaultObj值
public static <T> T requireNonNullElseGet(T obj, Supplier<? extends T> supplier)	// 检查对象是否不为null，如果不为null，返回该对象；如果															 // 为null,返回由Supplier所提供的值
```

<font color="blue" size="3">**2. 代码演示**</font>

```java
public class ObjectsDemo01 {
    public static void main(String[] args) {
        // 调用方法
    }

    // 测试nonNull方法
    public static void method_04() {
        Student s1 = new Student("itheima" , "14") ;
        boolean result = Objects.nonNull(s1);
        System.out.println(result);
    }

    // 测试isNull方法
    public static void method_03() {
        Student s1 = new Student("itheima" , "14") ;
        boolean result = Objects.isNull(s1);
        System.out.println(result);
    }

    // 测试equals方法
    public static void method_02() {
        // 创建两个学生对象
        Student s1 = new Student("itheima" , "14") ;
        Student s2 = new Student("itheima" , "14") ;
        boolean result = Objects.equals(s1, s2);  
        //细节：
        //1.方法的底层会判断s1是否为null，如果为null，直接返回false
        //2.如果s1不为null，那么利用s1再次调用equals方法
        //3.此时s1是Student类型，所以最终还是会调用Student中的equals方法
        //4.如果Student没有重写Object类中的equals方法，此处比较的还是对象的地址值
        System.out.println(result);
    }

    // 测试toString方法
    public static void method_01() {
        Student s1 = new Student("itheima" , "14") ;
        String result = Objects.toString(s1);       
        // 如果Student没有重写Object类中的toString方法，此处还是返回的对象的地址值
        System.out.println(result);
    }
}
```

```java
public class ObjectsDemo02 {
    public static void main(String[] args) {
        // 调用方法
    }

    // 演示requireNonNullElseGet
    public static void method_03() {
        Student s1 = new Student("itheima" , "14") ;
        // 该方法的第二个参数是Supplier类型的，查看源码发现Supplier是一个函数式接口,
        // 那么就可以为其传递一个Lambda表达式，
        // 而在Supplier接口中所定义的方法是无参有返回值的方法，因此具体调用所传入的Lambda表达式如下
        Student student = Objects.requireNonNullElseGet(s1, () -> {
            return new Student("itcast", "14");
        });
        System.out.println(student);
    }

    // 演示requireNonNullElse
    public static void method_02() {
        Student s1 = new Student("itheima" , "14") ;
        Student student = Objects.requireNonNullElse(s1, new Student("itcast", "14"));
        System.out.println(student);
    }

    // 演示requireNonNull
    public static void method_01() {
        Student s1 = new Student("itheima" , "14") ;
        Student student = Objects.requireNonNull(s1);
        System.out.println(student);
    }
}
```



## 8 BigInteger

平时在存储整数的时候，Java中默认是int类型，int类型有取值范围：-2147483648 ~ 2147483647。如果数字过大，可以使用long类型，但是如果long类型也表示不下怎么办呢？就需要用到BigInteger，可以理解为：**大的整数**。基本上在内存撑爆之前，都无法达到这个上限

BigInteger所在包是在java.math包下，因此在使用的时候就**需要进行导包**。

<font color="blue" size="3">**1. 构造方法**</font>

```java
public BigInteger(int num, Random rnd) 		//获取随机大整数，范围：[0 ~ 2的num次方-1]
public BigInteger(String val) 				//获取指定的大整数
public BigInteger(String val, int radix) 	//获取指定进制的大整数
    
下面这个不是构造，而是一个静态方法获取BigInteger对象
public static BigInteger valueOf(long val) 	//静态方法获取BigInteger的对象，内部有优化
```

**构造方法小结：**

* 如果BigInteger表示的数字没有超出long的范围，可以用静态方法获取
* 如果BigInteger表示的超出long的范围，可以用**构造方法**获取
* 对象一旦创建，BigInteger内部记录的值不能发生改变
* 只要进行计算都会产生一个**新的BigInteger对象**

<font color="blue" size="3">**2. 常见成员方法**</font>

BigDecimal类中使用最多的还是提供的进行四则运算的方法，如下：

```java
public BigInteger add(BigInteger val)					//加法
public BigInteger subtract(BigInteger val)				//减法
public BigInteger multiply(BigInteger val)				//乘法
public BigInteger divide(BigInteger val)				//除法
public BigInteger[] divideAndRemainder(BigInteger val)	 //除法，获取商和余数
public  boolean equals(Object x) 					    //比较是否相同
public  BigInteger pow(int exponent) 					//次幂、次方
public  BigInteger max/min(BigInteger val) 				//返回较大值/较小值
public  int intValue(BigInteger val) 					//转为int类型整数，超出范围数据有误
```

<font color="blue" size="3">**3. 代码示例**</font>

```java
//1.获取一个随机的大整数
Random r=new Random();
for (int i = e; i < 10; i++) { //获取10个随机数
    BigInteger bd1 = new BigInteger(4,r); //获取0~2^4-1之内的随机整数
    System.out.println(bd1);//[@ ~ 15]}
}
        
//2.获取一个指定的大整数，可以超出long的取值范围
//细节:字符串中必须是整数，否则会报错
//BigInteger bd2 = new BigInteger("1.1");//报错
//System.out.println(bd2);
//BigInteger bd3 = new BigInteger("abc");//报错
//System.out.println(bd3);
      
//3.获取指定进制的大整数
//细节:
//1.字符串中的数字必须是整数
//2.字符串中的数字必须要跟进制吻合
//比如二进制中，那么只能写0和1，写其他的就报错。
BigInteger bd4 = new BigInteger("123", 2);
System.out.println(bd4);

//4.静态方法获取BigInteger的对象，内部有优化
//细节:
//1.能表示范围比较小，只能在long的取值范围之内，如果超出long的范围就不行了
//2.在内部对常用的数字: -16 ~ 16 进行了优化
//  提前把-16~16 先创建好BigInteger的对象，如果多次获取不会重新创建新的
BigInteger bd5 = BigInteger.valueOf(16);
BigInteger bd6 = BigInteger.valueOf(16);
System.out.println(bd5 == bd6);//true

BigInteger bd7 = BigInteger.valueOf(17);
BigInteger bd8 = BigInteger.valueOf(17);
System.out.println(bd7 == bd8);//false

//5.对象一旦创建内部的数据不能发生改变
BigInteger bd9 =BigInteger.valueOf(1);
BigInteger bd10 =BigInteger.valueOf(2);
//此时，不会修改参与计算的BigInteger对象中的借，而是产生了一个新的BigInteger对象记录
BigInteger result=bd9.add(bd10);
System.out.println(result);//3
```

```java
import java.math.BigInteger;

public class BigIntegerDemo2 {
    public static void main(String[] args) {
        //1.创建两个BigInteger对象
        BigInteger bd1 = BigInteger.valueOf(10);
        BigInteger bd2 = BigInteger.valueOf(5);

        //2.加法
        BigInteger bd3 = bd1.add(bd2);
        System.out.println(bd3);

        //3.除法，获取商和余数
        BigInteger[] arr = bd1.divideAndRemainder(bd2);
        System.out.println(arr[0]);
        System.out.println(arr[1]);

        //4.比较是否相同
        boolean result = bd1.equals(bd2);
        System.out.println(result);

        //5.次幂
        BigInteger bd4 = bd1.pow(2);
        System.out.println(bd4);

        //6.max
        BigInteger bd5 = bd1.max(bd2);

        //7.转为int类型整数，超出范围数据有误
        /* BigInteger bd6 = BigInteger.valueOf(2147483647L);
         int i = bd6.intValue();
         System.out.println(i);*/

        BigInteger bd6 = BigInteger.valueOf(200);
        double v = bd6.doubleValue();
        System.out.println(v);//200.0
    }
}
```

<font color="blue" size="3">**4. 底层存储方式**</font>

对于计算机而言，其实是没有数据类型的概念的，都是0101010101，数据类型是编程语言自己规定的，所以在实际存储的时候，先把具体的数字变成二进制，每32个bit为一组，存储在数组中。 

数组中最多能存储元素个数：21亿多

数组中每一位能表示的数字：42亿多

理论上，BigInteger能表示的最大数字为：42亿的21亿次方。

但是还没到这个数字，电脑的内存就会撑爆，所以一般认为BigInteger是无限的。 

存储方式如图所示：

![bigInteger的底层原理](javaBasis_assets\37.png)

---



## 9 BigDecimal

首先来分析一下如下程序的执行结果：

```java
public class BigDecimalDemo01 {
    public static void main(String[] args) {
        System.out.println(0.09 + 0.01);
    }
}
```

这段代码比较简单，就是计算0.09和0.01之和，并且将其结果在控制台进行输出。那么按照我们的想法在控制台输出的结果应该为0.1。那么实际的运行结果是什么呢？我们来运行一下程序，控制台的输出

结果如下所示：

```java
0.09999999999999999
```

这样的结果其实就是一个丢失精度的结果。**为什么会产生精度丢失呢？**

在使用float或者double类型的数据在进行数学运算的时候，很有可能会产生精度丢失问题。我们都知道计算机底层在进行运算的时候，使用的都是二进制数据； 当我们在程序中写了一个十进制数据 ，在进行运算的时候，计算机会将这个十进制数据转换成二进制数据，然后再进行运算，计算完毕以后计算机会把运算的结果再转换成十进制数据给我们展示； 如果我们使用的是整数类型的数据进行计算，那么在把十进制数据转换成二进制数据的时候不会存在精度问题； 如果我们的数据是一个浮点类型的数据，有的时候计算机并不会将这个数据完全转换成一个二进制数据，而是将这个将其转换成一个无限的趋近于这个十进数的二进制数据； 这样使用一个不太准确的数据进行运算的时候， 最终就会造成精度丢失；为了提高精度，Java就提供了BigDecimal供我们进行数据运算。

![image-20240701102424302](javaBasis_assets\39.png)

![image-20240701102511825](javaBasis_assets\38.png)

BigDecimal所在包是在java.math包下，因此使用时需要导包。可以使用BigDecimal类进行更加精准的数据计算。

<font color="blue" size="3">**1. 构造方法**</font>

 ![1576134383441](javaBasis_assets\40.png)

<font color="blue" size="3">**2. 常见成员方法**</font>

BigDecimal类中使用最多的还是提供的进行四则运算的方法，如下：

```java
public BigDecimal add(BigDecimal value)				// 加法运算
public BigDecimal subtract(BigDecimal value)		// 减法运算
public BigDecimal multiply(BigDecimal value)		// 乘法运算
public BigDecimal divide(BigDecimal value)			// 触发运算
```

代码如下所示:

```java
public class BigDecimalDemo01 {
    public static void main(String[] args) {
        // 创建两个BigDecimal对象
        //细节：通过传递double型小数创建对象，可能造成不精确
        BigDecimal bd1 = new BigDecimal(0.01);
        BigDecimal bd2 = new BigDecimal(0.09);
        //通过字符串表示的小数创建对象不会丢失精度
        BigDecimal b1 = new BigDecimal("0.3") ;
        BigDecimal b2 = new BigDecimal("4") ;
        //通过静态方法获取对象
        BigDecimal bd6 = BigDecimal.valueOf(10);
        System.out.println(bd6);

        // 调用方法进行b1和b2的四则运算，并将其运算结果在控制台进行输出
        System.out.println(b1.add(b2));         // 进行加法运算
        System.out.println(b1.subtract(b2));    // 进行减法运算
        System.out.println(b1.multiply(b2));    // 进行乘法运算
        System.out.println(b1.divide(b2));      // 进行除法运算
        
        //细节：
        //1.如果要表示的数字不大，没有超出double取值范围，建议使用静态方法
        //2.如果表示的数字比较大，超出了double取值范围，建议使用构造方法
        //3.如果我们传递的是0-10之间的整数，包含0，包含10，那么方法会返回已经创建好的对象，不会重新new
    }
}
```

运行程序进行测试，控制台输出结果如下：

```java
4.3
-3.7
1.2
0.075
```

可以看到使用BigDecimal类来完成浮点数的计算不会存在损失精度的问题。

<font color="blue" size="3">**3. 除法的特殊情况**</font>

如果使用BigDecimal类型的数据进行除法运算的时候，得到的结果是一个无限循环小数，那么就会报错：ArithmeticException。 如下代码所示：

```java
public class BigDecimalDemo02 {
    public static void main(String[] args) {
        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("1") ;
        BigDecimal b2 = new BigDecimal("3") ;
        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2));
    }
}
```

运行程序进行测试，控制台输出结果如下所示：

```java
Exception in thread "main" java.lang.ArithmeticException: Non-terminating decimal expansion; no exact representable decimal result.
	at java.base/java.math.BigDecimal.divide(BigDecimal.java:1716)
	at com.itheima.api.bigdecimal.demo02.BigDecimalDemo02.main(BigDecimalDemo02.java:14)
```

针对这个问题怎么解决，此时我们就需要使用到BigDecimal类中另外一个divide方法，如下所示：

```java
BigDecimal divide(BigDecimal divisor, int scale, int roundingMode)
```

上述divide方法参数说明：

```
divisor:			除数对应的BigDecimal对象；
scale:				精确的位数；
roundingMode:		取舍模式；
取舍模式被封装到了RoundingMode这个枚举类中（关于枚举我们后期再做重点讲解），在这个枚举类中定义了很多种取舍方式。最常见的取舍方式有如下几个：
UP(直接进1) ， FLOOR(直接删除) ， HALF_UP(4舍五入),我们可以通过如下格式直接访问这些取舍模式：枚举类名.变量名
```

<font color="blue" size="3">**4. 取舍模式**</font>

```java
public class BigDecimalDemo02 {
    public static void main(String[] args) {
        // 调用方法
    }

    // 演示取舍模式HALF_UP
    public static void method_03() {
        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("0.3") ;
        BigDecimal b2 = new BigDecimal("4") ;
        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2 , 2 , RoundingMode.HALF_UP));
    }

    // 演示取舍模式FLOOR
    public static void method_02() {
        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("1") ;
        BigDecimal b2 = new BigDecimal("3") ;
        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2 , 2 , RoundingMode.FLOOR));
    }

    // 演示取舍模式UP
    public static void method_01() {
        // 创建两个BigDecimal对象
        BigDecimal b1 = new BigDecimal("1") ;
        BigDecimal b2 = new BigDecimal("3") ;
        // 调用方法进行b1和b2的除法运算，并且将计算结果在控制台进行输出
        System.out.println(b1.divide(b2 , 2 , RoundingMode.UP));
    }
}
```

> 小结：后期在进行两个数的除法运算的时候，常常使用的是可以设置取舍模式的divide方法。

<font color="blue" size="3">**5. 底层存储方式**</font>

把数据看成字符串，遍历得到里面的每一个字符，把这些字符在ASCII码表上的值，都存储到数组中。

![bigdecimal存储原理](javaBasis_assets\41.png)

---



## 10 正则表达式Pattern

在API帮助文档中找Pattern，查询相关表达式定义

### 10.1 字符类

| 符号               | 含义                                            |
| ------------------ | ----------------------------------------------- |
| \[abc\]            | 只能是a，b，c字符中的一个                       |
| \[^abc\]           | 除a,b,c以外的任何字符                           |
| [a-z]              | a-z的所有小写字符中的一个                       |
| [A-Z]              | A-Z的所有大写字符中的一个                       |
| [0-9]              | 0-9之间的某一个数字字符                         |
| [a-zA-Z0-9]        | a-z或者A-Z或者0-9之间的任意一个字符，包括(范围) |
| **[a-d[m-p]]**     | a 到 d 或 m 到 p之间的任意一个字符              |
| **[a-z&&[def]]**   | a-z和def的交集，为d,e,f                         |
| **[a-z&&\[^bc\]]** | a-z和非bc的交集，等同于[ad-z]                   |

```java
public class RegexDemo {
    public static void main(String[] args) {
        //public boolean matches(String regex):判断是否与正则表达式匹配，匹配返回true
        // 只能是a b c
        System.out.println("-----------1-------------");
        System.out.println("a".matches("[abc]")); // true
        System.out.println("z".matches("[abc]")); // false
        System.out.println("ab".matches("[abc]")); // false，只能出现一个字符
        System.out.println("ab".matches("[abc][abc]")); // true

        // 不能出现a b c
        System.out.println("-----------2-------------");
        System.out.println("a".matches("[^abc]")); // false
        System.out.println("z".matches("[^abc]")); // true
        System.out.println("zz".matches("[^abc][^abc]")); //true

        // a到zA到Z(包括头尾的范围)
        System.out.println("-----------3-------------");
        System.out.println("a".matches("[a-zA-z]")); // true
        System.out.println("zz".matches("[a-zA-Z][a-zA-Z]")); //true
        System.out.println("0".matches("[a-zA-Z0-9]"));//true

        // [a-d[m-p]] a到d，或m到p
        System.out.println("-----------4-------------");
        System.out.println("a".matches("[a-d[m-p]]"));//true
        System.out.println("m".matches("[a-d[m-p]]")); //true
        System.out.println("0".matches("[a-d[m-p]]")); //false

        // [a-z&&[def]] a-z和def的交集。为:d，e，f
        System.out.println("----------5------------");
        System.out.println("a".matches("[a-z&[def]]")); //false
        System.out.println("d".matches("[a-z&&[def]]")); //true

        // [a-z&&[^bc]] a-z和非bc的交集。(等同于[ad-z])
        System.out.println("-----------6------------_");
        System.out.println("a".matches("[a-z&&[^bc]]"));//true
        System.out.println("b".matches("[a-z&&[^bc]]")); //false

        // [a-z&&[^m-p]] a到z和除了m到p的交集。(等同于[a-1q-z])
        System.out.println("-----------7-------------");
        System.out.println("a".matches("[a-z&&[^m-p]]")); //true
        System.out.println("m".matches("[a-z&&[^m-p]]")); //false
    }
}
```



### 10.2 逻辑运算符

| 符号 | 含义     |
| ---- | -------- |
| &&   | 并且     |
| \|   | 或者     |
| \    | 转义字符 |

```java
public class Demo {
	public static void main(String[] args) {
		String str = "had";
		
		//1.要求字符串是小写辅音字符开头，后跟ad
		String regex = "[a-z&&[^aeiou]]ad";
		System.out.println("1." + str.matches(regex));
		
		//2.要求字符串是aeiou中的某个字符开头，后跟ad
		regex = "[a|e|i|o|u]ad";//这种写法相当于：regex = "[aeiou]ad";
		System.out.println("2." + str.matches(regex));
	}
}
```

```java
public class RegexDemo {
    public static void main(String[] args) {
        //1.要求以字符串的形式打印一个双引号
        //"在Java中表示字符串的开头或者结尾
        //此时\表示转义字符，改变了后面那个双引号原本的含义，变成了一个普普通通的双引号
        System.out.println("\"");

        // 2.要求以\表示转义字符
        //两个\的理解方式：前面的\是一个转义字符，改变了后面\原本的含义，把他变成一个普普通通的\
        System.out.println("c:Users\\moon\\IdeaProjects\\basic-code\\myapi\\src\\com\\itheima\\a08regexdemo\\RegexDemo1.java");
    }
}  
```



### 10.3 预定义字符

| 符号 | 含义                             |
| ---- | -------------------------------- |
| "."  | 匹配任何字符                     |
| \d"  | 任何数字[0-9]的简写              |
| "\D" | 任何非数字\[^0-9\]的简写         |
| "\s" | 空白字符：[ \t\n\x0B\f\r] 的简写 |
| "\S" | 非空白字符：\[^\s\] 的简写       |
| "\w" | 单词字符：[a-zA-Z_0-9]的简写     |
| "\W" | 非单词字符：\[^\w\]              |

```java
public class Demo {
	public static void main(String[] args) {
        //.表示任意一个字符
        System.out.println("你".matches("..")); //false
        System.out.println("你".matches(".")); //true
        System.out.println("你a".matches(".."));//true

        // \\d 表示任意的一个数字
        // 简单来记:两个\表示一个\
        System.out.println("a".matches("\\d")); // false
        System.out.println("3".matches("\\d")); // true
     
        //\\w只能是一位单词字符[a-zA-Z_0-9]
        System.out.println("z".matches("\\w")); // true
        System.out.println("你".matches("\\w"));//false

        // 非单词字符
        System.out.println("你".matches("\\W")); // true
        // 以上正则匹配只能校验单个字符

        // 必须是数字 字母 下划线 至少 6位
        System.out.println("2442fsfsf".matches("\\w{6,}"));//true
        System.out.println("244f".matches("\\w{6,}"));//false

        // 必须是数字和字符 必须是4位
        System.out.println("23dF".matches("[a-zA-Z0-9]{4}"));//true
        System.out.println("23 F".matches("[a-zA-Z0-9]{4}"));//false
        System.out.println("23dF".matches("[\\w&&[^_]]{4}"));//true
        System.out.println("23_F".matches("[\\w&&[^_]]{4}"));//false
	}
}
```



### 10.4 数量词

| 符号   | 含义                   |
| ------ | ---------------------- |
| X?     | 0次或1次               |
| X*     | 0次到多次              |
| X+     | 1次或多次1次或多次     |
| X{n}   | 恰好n次                |
| X{n,}  | 至少n次                |
| X{n,m} | n到m次(n和m都是包含的) |

```java
public class Demo {
	public static void main(String[] args) {
		 // 必须是数字 字母 下划线 至少 6位
        System.out.println("2442fsfsf".matches("\\w{6,}"));//true
        System.out.println("244f".matches("\\w{6,}"));//false

        // 必须是数字和字符 必须是4位
        System.out.println("23dF".matches("[a-zA-Z0-9]{4}"));//true
        System.out.println("23 F".matches("[a-zA-Z0-9]{4}"));//false
        System.out.println("23dF".matches("[\\w&&[^_]]{4}"));//true
        System.out.println("23_F".matches("[\\w&&[^_]]{4}"));//false
	}
}
```

###### 练习1：编写正则表达式

​	请编写正则表达式验证用户输入的手机号码是否满足要求。

​	请编写正则表达式验证用户输入的邮箱号是否满足要求。

​	请编写正则表达式验证用户输入的电话号码是否满足要求。

​	验证手机号码 13112345678 13712345667 13945679027 139456790271

​	验证座机电话号码 020-2324242 02122442 027-42424 0712-3242434

​	验证邮箱号码 3232323@qq.com zhangsan@itcast.cnn dlei0009@163.com dlei0009@pci.com.cn

```java
public class RegexDemo {
    public static void main(String[] args) {
        //13112345678
        //分成三部分:
        //第一部分:1 表示手机号码只能以1开头
        //第二部分:[3-9] 表示手机号码第二位只能是3-9之间的
        //第三部分:\\d{9} 表示任意数字可以出现9次，也只能出现9次
        String regex1 = "1[3-9]\\d{9}";
        System.out.println("13112345678".matches(regex1));//true
        System.out.println("13712345667".matches(regex1));//true
        System.out.println("13945679027".matches(regex1));//true
        System.out.println("139456790271".matches(regex1));//false
        System.out.println("-----------------------------------");

        //座机电话号码
        //020-2324242 02122442 027-42424 0712-3242434
        //在书写座机号正则的时候需要把正确的数据分为三部分
        //一:区号@\\d{2,3}
        //      0:表示区号一定是以0开头的
        //      \\d{2,3}:表示区号从第二位开始可以是任意的数字，可以出现2到3次。
        //二:- ?表示次数，日次或一次
        //三:号码 号码的第一位也不能以日开头，从第二位开始可以是任意的数字，号码的总长度:5-10位
        String regex2 = "0\\d{2,3}-?[1-9]\\d{4,9}";
        System.out.println("020-2324242".matches(regex2));
        System.out.println("02122442".matches(regex2));
        System.out.println("027-42424".matches(regex2));
        System.out.println("0712-3242434".matches(regex2));

        //邮箱号码
        //3232323@qq.com zhangsan@itcast.cnn dlei0009@163.com dlei0009@pci.com.cn
        //在书写邮箱号码正则的时候需要把正确的数据分为三部分
        //第一部分:@的左边 \\w+
        //      任意的字母数字下划线，至少出现一次就可以了
        //第二部分:@ 只能出现一次
        //第三部分:
        //      3.1         .的左边[\\w&&[^_]]{2,6}
        //                  任意的字母加数字，总共出现2-6次(此时不能出现下划线)
        //      3.2         . \\.
        //      3.3         大写字母，小写字母都可以，只能出现2-3次[a-zA-Z]{2,3}
        //      我们可以把3.2和3.3看成一组，这一组可以出现1次或者两次
        String regex3 = "\\w+@[\\w&&[^_]]{2,6}(\\.[a-zA-Z]{2,3}){1,2}";
        System.out.println("3232323@qq.com".matches(regex3));
        System.out.println("zhangsan@itcast.cnn".matches(regex3));
        System.out.println("dlei0009@163.com".matches(regex3));
        System.out.println("dlei0009@pci.com.cn".matches(regex3));

        //24小时的正则表达式
        String regex4 = "([01]\\d|2[0-3]):[0-5]\\d:[0-5]\\d";
        System.out.println("23:11:11".matches(regex4));

        String regex5 = "([01]\\d 2[0-3])(:[0-5]\\d){2}";
        System.out.println("23:11:11".matches(regex5));
    }
}
```

###### 练习2：判断身份证格式

​	请编写正则表达式验证用户名是否满足要求。要求:大小写字母，数字，下划线一共4-16位
​	请编写正则表达式验证身份证号码是否满足要求
​	简单要求:18位，前17位任意数字，最后一位可以是数字可以是大写或小写的x
​	复杂要求:按照身份证号码的格式严格要求

​	身份证号码:
​		41080119930228457x
​		510801197609022309
​		15040119810705387X
​		130133197204039024 
​		430102197606046442

```java
public class RegexDemo {
    public static void main(String[] args) {
        //用户名要求:大小写字母，数字，下划线一共4-16位
        String regex1 = "\\w{4,16}";
        System.out.println("zhangsan".matches(regex1));
        System.out.println("lisi".matches(regex1));
        System.out.println("wangwu".matches(regex1));
        System.out.println("$123".matches(regex1));

        //身份证号码的简单校验:
        //18位，前17位任意数字，最后一位可以是数字可以是大写或小写的x
        String regex2 = "[1-9]\\d{16}(\\d|x|x)";
        String regex3 = "[1-9]\\d{16}[\\dXx]";
        String regex5 = "[1-9]\\d{16}(\\d(?i)x)";

        System.out.println("41080119930228457x".matches(regex3));
        System.out.println("510801197609022309".matches(regex3));
        System.out.println("15040119810705387X".matches(regex3));
        System.out.println("130133197204039024".matches(regex3));
        System.out.println("430102197606046442".matches(regex3));

        //忽略大小写的书写方式
        //在匹配的时候忽略abc的大小写
        String regex4 = "a((?i)b)c";
        System.out.println("------------------------------");
        System.out.println("abc".matches(regex4));//true
        System.out.println("ABC".matches(regex4));//false
        System.out.println("aBc".matches(regex4));//true

        //身份证号码的严格校验
        //编写正则的小心得:
        //第一步:按照正确的数据进行拆分
        //第二步:找每一部分的规律，并编写正则表达式
        //第三步:把每一部分的正则拼接在一起，就是最终的结果
        //书写的时候:从左到右去书写。

        //410801 1993 02 28 457x
        //前面6位:省份，市区，派出所等信息，第一位不能是0，后面5位是任意数字       [1-9]\\d{5}
        //年的前半段: 18 19 20                                                (18|19|20)
        //年的后半段: 任意数字出现两次                                           \\d{2}
        //月份: 01~ 09 10 11 12                                               (@[1-9]|1[0-2])
        //日期: 01~09 10~19 20~29 30 31                                       (0[1-9]|[12]\\d|3[01])
        //后面四位: 任意数字出现3次 最后一位可以是数字也可以是大写x或者小写x        \\d{3}[\\dXx]
        String regex6 = "[1-9]\\d{5}(18|19|20)\\d{2}(@[1-9]|1[0-2])(@[1-9]|[12]\\d|3[01])\\d{3}[\\dxXx]";

        System.out.println("41080119930228457x".matches(regex6));
        System.out.println("510801197609022309".matches(regex6));
        System.out.println("15040119810705387X".matches(regex6));
        System.out.println("130133197204039024".matches(regex6));
        System.out.println("430102197606046442".matches(regex6));
    }
}
```

**正则表达式小结**

| 符号      | 含义                   |
| --------- | ---------------------- |
| []        | 里面的内容出现一次     |
| ()        | 分组                   |
| ^         | 取反                   |
| &&        | 交集，不能写单个的&    |
| \|        | 写在方括号外面表示并集 |
| .         | 任意字符               |
| \         | 转义字符               |
| \\d       | 0-9                    |
| \\D       | 非0-9                  |
| \\s       | 空白字符               |
| \\S       | 非空白字符             |
| \\w       | 单词字符               |
| \\W       | 非单词字符             |
| ？        | 0次或1次               |
| *         | 0次或多次              |
| +         | 1次或多次              |
| {}        | 具体次数               |
| (?!)      | 忽略后面字符的大小写   |
| a((?!)b)c | 只忽略b的大小写        |



### 10.5 数据爬取

#### 10.5.1 本地数据爬取

**Matcher**：**文本匹配器**，按照正则表达式的规则读取字符串，从头开始读取。在大串中去找符合匹配规则的子串

**要求**：有如下文本，请按照要求爬取数据。“Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台”。找出里面所有的JavaXX

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexDemo {
    public static void main(String[] args) {
        String str = "Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，" +"因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台";

        //1.获取正则表达式的对象
        Pattern p = Pattern.compile("Java\\d{0,2}");
        //2.获取文本匹配器的对象
        //拿着m去读取str，找符合p规则的子串
        Matcher m = p.matcher(str);
        //3.利用循环获取
        while (m.find()) {
            String s = m.group();
            System.out.println(s);
        }
    }

    private static void method1(String str) {
        //获取正则表达式的对象
        Pattern p = Pattern.compile("Java\\d{0,2}");
        //获取文本匹配器的对象
        //m:文本匹配器的对象
        //str:大串
        //p:规则
        //m要在str中找符合p规则的小串
        Matcher m = p.matcher(str);

        //拿着文本匹配器从头开始读取，寻找是否有满足规则的子串
        //如果没有，方法返回false
        //如果有，返回true。在底层记录子串的起始索引和结束索引+1
        // 0,4
        boolean b = m.find();

        //方法底层会根据find方法记录的索引进行字符串的截取
        // substring(起始索引，结束索引);包头不包尾
        // (0,4)但是不包含4索引
        // 会把截取的小串进行返回。
        String s1 = m.group();
        System.out.println(s1);

        //第二次在调用find的时候，会继续读取后面的内容
        //读取到第二个满足要求的子串，方法会继续返回true
        //并把第二个子串的起始索引和结束索引+1，进行记录
        b = m.find();

        //第二次调用group方法的时候，会根据find方法记录的索引再次截取子串
        String s2 = m.group();
        System.out.println(s2);
    }
}
```

#### 10.5.2 网络数据爬取

**需求**：把连接:https://m.sengzan.com/jiaoyu/29104.html?ivk sa=1025883i中所有的身份证号码都爬取出来

```java
public class RegexDemo {
    public static void main(String[] args) throws IOException {
        //创建一个URL对象
        URL url = new URL("https://m.sengzan.com/jiaoyu/29104.html?ivk sa=1025883i");
        //连接上这个网址
        //细节:保证网络是畅通
        URLConnection conn = url.openConnection();//创建一个对象去读取网络中的数据
        BufferedReader br = new BufferedReader(new  InputStreamReader(conn.getInputStream()));
        String line;
        //获取正则表达式的对象pattern
        String regex = "[1-9]\\d{17}";
        Pattern pattern = Pattern.compile(regex);//在读取的时候每次读一整行
        while ((line = br.readLine()) != null) {
            //拿着文本匹配器的对象matcher按照pattern的规则去读取当前的这一行信息
            Matcher matcher = pattern.matcher(line);
            while (matcher.find()) {
                System.out.println(matcher.group());
            }
        }
        br.close();
    }
}
```

###### 练习1：爬取数据

**需求**：把下面文本中的座机电话，邮箱，手机号，热线都爬取出来。

来黑马程序员学习Java，手机号:18512516758，18512508907或者联系邮箱:boniu@itcast.cn，座机电话:01036517895，010-98951256邮箱:bozai@itcast.cn，热线电话:400-618-9090 ，400-618-4000，4006184000，4006189090手机号的正则表达式:1[3-9]\d{9}

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexDemo8 {
    public static void main(String[] args) {
        String s = "来黑马程序员学习Java，" +
                "电话:18512516758，18512508907" + "或者联系邮箱:boniu@itcast.cn，" +
                "座机电话:01036517895，010-98951256" + "邮箱:bozai@itcast.cn，" +
                "热线电话:400-618-9090 ，400-618-4000，4006184000，4006189090";
        System.out.println("400-618-9090");
        String regex = "(1[3-9]\\d{9})|(\\w+@[\\w&&[^_]]{2,6}(\\.[a-zA-Z]{2,3}){1,2})" +
                "|(0\\d{2,3}-?[1-9]\\d{4,9})" +
                "(400-?[1-9]\\d{2}-?[1-9]\\d{3})";
        //1.获取正则表达式的对象
        Pattern p = Pattern.compile(regex);
        //2.获取文本匹配器的对象
        //利用m去读取s，会按照p的规则找里面的小串
        Matcher m = p.matcher(s);
        //3.利用循环获取每一个数据 while(m.find()){
        String str = m.group();
        System.out.println(str);
    }
}
```

###### 练习2：按要求爬取

**需求**：有如下文本，按要求爬取数据。   

​	 Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台。

需求1：爬取版本号为8，11.17的Java文本，但是只要Java，不显示版本号。

需求2：爬取版本号为8，11，17的Java文本。正确爬取结果为：Java8 Java11 Java17 Java17

需求3：爬取除了版本号为8，11，17的Java文本。

```java
public class RegexDemo9 {
    public static void main(String[] args) {
        String s = "Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，" +
            "因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台";

        //1.定义正则表达式
        //?理解为前面的数据Java
        //=表示在Java后面要跟随的数据
        //但是在获取的时候，只获取前半部分
        //需求1:
        String regex1 = "((?i)Java)(?=8|11|17)";
        //需求2:
        String regex2 = "((?i)Java)(8|11|17)";
        String regex3 = "((?i)Java)(?:8|11|17)";
        //需求3:
        String regex4 = "((?i)Java)(?!8|11|17)";

        Pattern p = Pattern.compile(regex4);
        Matcher m = p.matcher(s);
        while (m.find()) {
            System.out.println(m.group());
        }
    }
}
```

#### 10.5.3 贪婪和非贪婪爬取

```java
只写+和表示贪婪匹配，如果在+和后面加问号表示非贪婪爬取
+? 非贪婪匹配
*? 非贪婪匹配
贪婪爬取:在爬取数据的时候尽可能的多获取数据
非贪婪爬取:在爬取数据的时候尽可能的少获取数据

举例：
如果获取数据：ab+
贪婪爬取获取结果:abbbbbbbbbbbb
非贪婪爬取获取结果:ab
```

代码示例：

```java
public class RegexDemo10 {
    public static void main(String[] args) {
        String s = "Java自从95年问世以来，abbbbbbbbbbbbaaaaaaaaaaaaaaaaaa" +
                "经历了很多版木，目前企业中用的最多的是]ava8和]ava11，因为这两个是长期支持版木。" +
                "下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台";

        String regex = "ab+";
        Pattern p = Pattern.compile(regex);
        Matcher m = p.matcher(s);

        while (m.find()) {
            System.out.println(m.group());
        }
    }
}
```

### 10.6 String类使用正则

<font color=blue>**1. String的split方法中使用正则**</font>

- String类的split()方法原型：

  ```java
  public String[] split(String regex)
  //参数regex表示正则表达式。可以将当前字符串中匹配regex正则表达式的符号作为"分隔符"来切割字符串。
  ```

- 代码示例：

  有一段字符串:小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠
  要求1:把字符串中三个姓名之间的字母替换为vs
  要求2:把字符串中的三个姓名切割出来

```java
String s = "小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠";
//细节:
//方法在底层跟之前一样也会创建文本解析器的对象
//然后从头开始去读取字符串中的内容，只要有满足的，那么就切割。
String[] arr = s.split("[\\w&&[^_]]+");
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

<font color=blue>**2. String的replaceAll方法中使用正则**</font>

- String类的replaceAll()方法原型：

```java
public String replaceAll(String regex,String newStr)
//参数regex表示一个正则表达式。可以将当前字符串中匹配regex正则表达式的字符串替换为newStr。
```

- 代码示例：

  有一段字符串:小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠
  要求1:把字符串中三个姓名之间的字母替换为vs
  要求2:把字符串中的三个姓名切割出来

```java
String s = "小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠";

String result1 = s.replaceAll("[\\w&&[^_]]+", "vs");
System.out.println(result1);
```

### 10.7 分组括号( )

细节：如何识别组号？

规则：正则表达式中每组都有组好，即序号

​	规则1：从1开始，连续不间断

​	规则2：以左括号为基准，最左边是第一组，其次为第二组，依次类推

只看左括号，不看右括号，按照左括号的顺序，从左往右，依次为第一组，第二组，第三组等等

```java
//需求1:判断一个字符串的开始字符和结束字符是否一致?只考虑一个字符
//举例: a123a b456b 17891 &abc& a123b(false)
// \\组号:表示把第X组的内容再出来用一次
String regex1 = "(.).+\\1"; //表示首字母任意.并且单独分为1组(.),第二个字母.+代码大于1的字符
//1 将第一组数据再用一次
System.out.println("a123a".matches(regex1));
System.out.println("b456b".matches(regex1));
System.out.println("17891".matches(regex1));
System.out.println("&abc&".matches(regex1));
System.out.println("a123b".matches(regex1));
System.out.println("--------------------------");

//需求2:判断一个字符串的开始部分和结束部分是否一致?可以有多个字符
//举例: abc123abc b456b 123789123 &!@abc&!@ abc123abd(false)
String regex2 = "(.+).+\\1";
System.out.println("abc123abc".matches(regex2));
System.out.println("b456b".matches(regex2));
System.out.println("123789123".matches(regex2));
System.out.println("&!@abc&!@".matches(regex2));
System.out.println("abc123abd".matches(regex2));
System.out.println("---------------------");

//需求3:判断一个字符串的开始部分和结束部分是否一致?开始部分内部每个字符也需要一致
//举例: aaa123aaa bbb456bbb 111789111 &&abc&&
//(.):把首字母看做一组
// \\2:把首字母拿出来再次使用
// *:作用于\\2,表示后面重复的内容出现日次或多次
String regex3 = "((.)\\2*).+\\1";
System.out.println("aaa123aaa".matches(regex3));
System.out.println("bbb456bbb".matches(regex3));
System.out.println("111789111".matches(regex3));
System.out.println("&&abc&&".matches(regex3));
System.out.println("aaa123aab".matches(regex3));
```

###### 练习1：字符串替换 

将字符串：我要学学编编编编程程程程程程.。替换为：我要学编程

```java
String str = "我要学学编编编编程程程程程程";

//需求:把重复的内容 替换为 单个的
//学学                学
//编编编编            编
//程程程程程程        程
//  (.)表示把重复内容的第一个字符看做一组
//  \\1表示第一字符再次出现
//  + 至少一次
//  $1 表示把正则表达式中第一组的内容，再拿出来用
String result = str.replaceAll("(.)\\1+", "$1");
System.out.println(result);
```

######  练习2：忽略大小写

```java
//(?i) ：表示忽略后面数据的大小写
//忽略abc的大小写
String regex = "(?i)abc";
//a需要一模一样，忽略bc的大小写
String regex = "a(?i)bc";
//ac需要一模一样，忽略b的大小写
String regex = "a((?i)b)c";
```

###### 练习3：非捕获分组

非捕获分组：分组之后不需要再用本组数据，仅仅是把数据括起来。

```java
//身份证号码的简易正则表达式
//非捕获分组:仅仅是把数据括起来
//特点:不占用组号
//这里\\1报错原因:(?:)就是非捕获分组，此时是不占用组号的。

//(?:) (?=) (?!)都是非捕获分组//更多的使用第一个
//String regex1 ="[1-9]\\d{16}(?:\\d|x|x)\\1";
String regex2 ="[1-9]\\d{16}(\\d Xx)\\1";
//^([01]\d|2[0-3]):[0-5]\d:[@-5]\d$

System.out.println("41080119930228457x".matches(regex2));
```

**练习总结：**

```java
手机号码:1[3-9]\\d{9}
座机号码：0\\d{2,3}-?[1-9]\\d{4,9}
邮箱号码：\\w+@[\\w&&[^_]]{2,6}(\\.[a-zA-Z]{2,3}){1,2}
24小时：([01]\\d|2[0-3]):[0-5]\\d:[0-5]\\d
	   ([01]\\d|2[0-3])(:[0-5]\\d){2}
用户名:	\\w{4,16}
身份证号码，简单校验：
		[1-9]\\d{16}(\\d|X|x)
		[1-9]\\d{16}[\\dXx]
		[1-9]\\d{16}(\\d(?i)X)
身份证号码，严格校验：
		[1-9]\\d{5}(18|19|20)\\d{2}(0[1-9]|1[0-2])(0[1-9|[12])\\d|3[01])\\d{3}[\\dXx]
```

---



## 11 时间类

### 11.1 Date

java.util.Date类 表示特定的瞬间，精确到毫秒

Date拥有多个构造函数，只是部分已经过时，重点有两个构造函数：

- `public Date()`：从运行程序的此时此刻到时间原点经历的毫秒值,转换成Date对象，分配Date对象并初始化此对象，以表示分配它的时间（精确到毫秒）
- `public Date(long date)`：将指定参数的毫秒值date,转换成Date对象，分配Date对象并初始化此对象，以表示自从标准基准时间（称为“历元（epoch）”，即1970年1月1日00:00:00 GMT）以来的指定毫秒数

> tips: 由于中国处于东八区（GMT+08:00）是比世界协调时间/格林尼治时间（GMT）快8小时的时区，当格林尼治标准时间为0:00时，东八区的标准时间为08:00。

简单来说：使用无参构造，可以自动设置当前系统时间的毫秒时刻；指定long类型的构造参数，可以自定义毫秒时刻。例如：

```java
public class Demo01Date {
    public static void main(String[] args) {
        // 创建日期对象，把当前的时间
        System.out.println(new Date()); // Tue Jan 16 14:37:35 CST 2020
        // 创建日期对象，把当前的毫秒值转成日期对象
        System.out.println(new Date(0L)); // Thu Jan 01 08:00:00 CST 1970
    }
}
```

> tips:在使用println方法时，会自动调用Date类中的toString方法。Date类对Object类中的toString方法进行了覆盖重写，所以结果为指定格式的字符串。

Date类中的多数方法已经过时，常用的方法有：

- `public long getTime()` 把日期对象转换成对应的时间毫秒值。
- `public void setTime(long time)` 把方法参数给定的毫秒值设置给日期对象

```java
public class DateDemo02 {
    public static void main(String[] args) {
        //创建日期对象
        Date d = new Date();
        
        //public long getTime():获取的是日期对象从1970年1月1日 00:00:00到现在的毫秒值
        //System.out.println(d.getTime());
        //System.out.println(d.getTime() * 1.0 / 1000 / 60 / 60 / 24 / 365 + "年");

        //public void setTime(long time):设置时间，给的是毫秒值
        //long time = 1000*60*60;
        long time = System.currentTimeMillis();
        d.setTime(time);

        System.out.println(d);
    }
}
```

> 小结：Date表示特定的时间瞬间，可以使用Date对象对时间进行操作。



### 11.2 SimpleDateFormat

`java.text.SimpleDateFormat` 是日期/时间格式化类，通过这个类可以完成日期和文本之间的转换,也就是可以在Date对象与String对象之间进行来回转换。

- **格式化**：按照指定的格式，把Date对象转换为String对象。
- **解析**：按照指定的格式，把String对象转换为Date对象。

由于DateFormat为抽象类，不能直接使用，所以需要常用的子类`java.text.SimpleDateFormat`。这个类需要一个模式（格式）来指定格式化或解析的标准。构造方法为：

- `public SimpleDateFormat(String pattern)`：用给定的模式和默认语言环境的日期格式符号构造SimpleDateFormat。参数pattern是一个字符串，代表日期时间的自定义格式。

常用的格式规则为：

| 标识字母（区分大小写） | 含义 |
| ---------------------- | ---- |
| y                      | 年   |
| M                      | 月   |
| d                      | 日   |
| H                      | 时   |
| m                      | 分   |
| s                      | 秒   |

DateFormat类的常用方法有：

- `public String format(Date date)`：将Date对象格式化为字符串。

- `public Date parse(String source)`：将字符串解析为Date对象。

  ```java
  import java.text.ParseException;
  import java.text.SimpleDateFormat;
  import java.util.Date;
  
  public class A03_SimpleDateFormatDemo1 {
      public static void main(String[] args) throws ParseException {
          /*
              public simpleDateFormat() 默认格式
              public simpleDateFormat(String pattern) 指定格式
              public final string format(Date date) 格式化(日期对象 ->字符串)
              public Date parse(string source) 解析(字符串 ->日期对象)
          */
  
          //1.定义一个字符串表示时间
          String str = "2023-11-11 11:11:11";
          //2.利用空参构造创建simpleDateFormat对象
          // 细节:
          //创建对象的格式要跟字符串的格式完全一致
          SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
          Date date = sdf.parse(str);
          //3.打印结果
          System.out.println(date.getTime());//1699672271000
      }
  
      private static void method1() {
          //1.利用空参构造创建simpleDateFormat对象，默认格式
          SimpleDateFormat sdf1 = new SimpleDateFormat();
          Date d1 = new Date(0L);
          String str1 = sdf1.format(d1);
          System.out.println(str1);//1970/1/1 上午8:00
  
          //2.利用带参构造创建simpleDateFormat对象，指定格式
          SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy年MM月dd日HH:mm:ss");
          String str2 = sdf2.format(d1);
          System.out.println(str2);//1970年01月01日 08:00:00
  
          //课堂练习:yyyy年MM月dd日 时:分:秒 星期
      }
  }
  
  ```

> 小结：DateFormat可以将Date对象和字符串相互转换。

###### 练习1：出生日期

```java
/*
     假设，你初恋的出生年月日为:2000-11-11
     请用字符串表示这个数据，并将其转换为:2000年11月11日

     创建一个Date对象表示2000年11月11日
     创建一个SimpleDateFormat对象，并定义格式为年月日把时间变成:2000年11月11日
*/

//1.可以通过2000-11-11进行解析，解析成一个Date对象
String str = "2000-11-11";
//2.解析
SimpleDateFormat sdf1 = new SimpleDateFormat("yyyy-MM-dd");
Date date = sdf1.parse(str);
//3.格式化
SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy年MM月dd日");
String result = sdf2.format(date);
System.out.println(result);
```

###### 练习2：秒杀活动

```java
/* 需求:
            秒杀活动开始时间:2023年11月11日 0:0:0(毫秒值)
            秒杀活动结束时间:2023年11月11日 0:10:0(毫秒值)

            小贾下单并付款的时间为:2023年11月11日 0:01:0
            小皮下单并付款的时间为:2023年11月11日 0:11:0
            用代码说明这两位同学有没有参加上秒杀活动?
         */

//1.定义字符串表示三个时间
String startstr = "2023年11月11日 0:0:0";
String endstr = "2023年11月11日 0:10:0";
String orderstr = "2023年11月11日 0:01:00";
//2.解析上面的三个时间，得到Date对象
SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日HH:mm:ss");
Date startDate = sdf.parse(startstr);
Date endDate = sdf.parse(endstr);
Date orderDate = sdf.parse(orderstr);

//3.得到三个时间的毫秒值
long startTime = startDate.getTime();
long endTime = endDate.getTime();
long orderTime = orderDate.getTime();

//4.判断
if (orderTime >= startTime && orderTime <= endTime) {
    System.out.println("参加秒杀活动成功");
} else {
    System.out.println("参加秒杀活动失败");
}
```

### 11.3 Calendar

- java.util.Calendar类表示一个“日历类”，可以进行日期运算。它是一个抽象类，不能创建对象，我们可以使用它的子类：java.util.GregorianCalendar类。
- 有两种方式可以获取GregorianCalendar对象：
  - 直接创建GregorianCalendar对象；
  - 通过Calendar的静态方法getInstance()方法获取GregorianCalendar对象

| 方法名                                | 说明                                                         |
| ------------------------------------- | ------------------------------------------------------------ |
| public static Calendar getInstance()  | 获取一个它的子类GregorianCalendar对象。                      |
| public int get(int field)             | 获取某个字段的值。field参数表示获取哪个字段的值，<br />可以使用Calender中定义的常量来表示：<br />Calendar.YEAR : 年<br />Calendar.MONTH ：月<br />Calendar.DAY_OF_MONTH：月中的日期<br />Calendar.HOUR：小时<br />Calendar.MINUTE：分钟<br />Calendar.SECOND：秒<br />Calendar.DAY_OF_WEEK：星期 |
| public void set(int field,int value)  | 设置某个字段的值                                             |
| public void add(int field,int amount) | 为某个字段增加/减少指定的值                                  |

```java
public class Demo {
    public static void main(String[] args) {
        //1.获取一个GregorianCalendar对象
        Calendar instance = Calendar.getInstance();//获取子类对象

        //2.打印子类对象
        System.out.println(instance);

        //3.获取属性
        int year = instance.get(Calendar.YEAR);
        int month = instance.get(Calendar.MONTH) + 1;//Calendar的月份值是0-11
        int day = instance.get(Calendar.DAY_OF_MONTH);

        int hour = instance.get(Calendar.HOUR);
        int minute = instance.get(Calendar.MINUTE);
        int second = instance.get(Calendar.SECOND);

        int week = instance.get(Calendar.DAY_OF_WEEK);//返回值范围：1--7，分别表示："星期日","星期一","星期二",...,"星期六"

        System.out.println(year + "年" + month + "月" + day + "日" + 
                           	hour + ":" + minute + ":" + second);
        System.out.println(getWeek(week));

    }

    //查表法，查询星期几
    public static String getWeek(int w) {//w = 1 --- 7
        //做一个表(数组)
        String[] weekArray = {"星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"};
        //索引      [0]      [1]       [2]      [3]       [4]      [5]      [6]
        //查表
        return weekArray[w - 1];
    }
}
```

```java
public class Demo {
    public static void main(String[] args) {
        //设置属性——set(int field,int value):
		Calendar c1 = Calendar.getInstance();//获取当前日期

		//计算班长出生那天是星期几(假如班长出生日期为：1998年3月18日)
		c1.set(Calendar.YEAR, 1998);
		c1.set(Calendar.MONTH, 3 - 1);//转换为Calendar内部的月份值
		c1.set(Calendar.DAY_OF_MONTH, 18);

		int w = c1.get(Calendar.DAY_OF_WEEK);
		System.out.println("班长出生那天是：" + getWeek(w));      
    }
    //查表法，查询星期几
    public static String getWeek(int w) {//w = 1 --- 7
        //做一个表(数组)
        String[] weekArray = {"星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"};
        //索引      [0]      [1]       [2]      [3]       [4]      [5]      [6]
        //查表
        return weekArray[w - 1];
    }
}
```

```java
public class Demo {
    public static void main(String[] args) {
        //计算200天以后是哪年哪月哪日，星期几？
		Calendar c2 = Calendar.getInstance();//获取当前日期
        c2.add(Calendar.DAY_OF_MONTH, 200);//日期加200

        int y = c2.get(Calendar.YEAR);
        int m = c2.get(Calendar.MONTH) + 1;//转换为实际的月份
        int d = c2.get(Calendar.DAY_OF_MONTH);

        int wk = c2.get(Calendar.DAY_OF_WEEK);
        System.out.println("200天后是：" + y + "年" + m + "月" + d + "日" + getWeek(wk));

    }
    //查表法，查询星期几
    public static String getWeek(int w) {//w = 1 --- 7
        //做一个表(数组)
        String[] weekArray = {"星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"};
        //索引      [0]      [1]       [2]      [3]       [4]      [5]      [6]
        //查表
        return weekArray[w - 1];
    }
}
```

### 11.4 JDK8时间相关类

| JDK8时间类类名    | 作用                   |
| ----------------- | ---------------------- |
| ZoneId            | 时区                   |
| Instant           | 时间戳                 |
| ZoneDateTime      | 带时区的时间           |
| DateTimeFormatter | 用于时间的格式化和解析 |
| LocalDate         | 年、月、日             |
| LocalTime         | 时、分、秒             |
| LocalDateTime     | 年、月、日、时、分、秒 |
| Duration          | 时间间隔（秒，纳，秒） |
| Period            | 时间间隔（年，月，日） |
| ChronoUnit        | 时间间隔（所有单位）   |

<font color=blue>**1. ZoneId 时区**</font>

```java
/*
        static Set<string> getAvailableZoneIds() 获取Java中支持的所有时区
        static ZoneId systemDefault() 获取系统默认时区
        static Zoneld of(string zoneld) 获取一个指定时区*/

//1.获取所有的时区名称
Set<String> zoneIds = ZoneId.getAvailableZoneIds();
System.out.println(zoneIds.size());//600
System.out.println(zoneIds);// Asia/Shanghai

//2.获取当前系统的默认时区
ZoneId zoneId = ZoneId.systemDefault();
System.out.println(zoneId);//Asia/Shanghai

//3.获取指定的时区
ZoneId zoneId1 = ZoneId.of("Asia/Pontianak");
System.out.println(zoneId1);//Asia/Pontianak
```

<font color=blue>**2. Instant 时间戳**</font>

```java
/*
            static Instant now() 获取当前时间的Instant对象(标准时间)
            static Instant ofXxxx(long epochMilli) 根据(秒/毫秒/纳秒)获取Instant对象
            ZonedDateTime atZone(ZoneIdzone) 指定时区
            boolean isxxx(Instant otherInstant) 判断系列的方法
            Instant minusXxx(long millisToSubtract) 减少时间系列的方法
            Instant plusXxx(long millisToSubtract) 增加时间系列的方法*/
//1.获取当前时间的Instant对象(标准时间)
Instant now = Instant.now();
System.out.println(now);

//2.根据(秒/毫秒/纳秒)获取Instant对象
Instant instant1 = Instant.ofEpochMilli(0L);
System.out.println(instant1);//1970-01-01T00:00:00z

Instant instant2 = Instant.ofEpochSecond(1L);
System.out.println(instant2);//1970-01-01T00:00:01Z

Instant instant3 = Instant.ofEpochSecond(1L, 1000000000L);
System.out.println(instant3);//1970-01-01T00:00:027

//3. 指定时区
ZonedDateTime time = Instant.now().atZone(ZoneId.of("Asia/Shanghai"));
System.out.println(time);


//4.isXxx 判断
Instant instant4=Instant.ofEpochMilli(0L);
Instant instant5 =Instant.ofEpochMilli(1000L);

//5.用于时间的判断
//isBefore:判断调用者代表的时间是否在参数表示时间的前面
boolean result1=instant4.isBefore(instant5);
System.out.println(result1);//true

//isAfter:判断调用者代表的时间是否在参数表示时间的后面
boolean result2 = instant4.isAfter(instant5);
System.out.println(result2);//false

//6.Instant minusXxx(long millisToSubtract) 减少时间系列的方法
Instant instant6 =Instant.ofEpochMilli(3000L);
System.out.println(instant6);//1970-01-01T00:00:03Z

Instant instant7 =instant6.minusSeconds(1);
System.out.println(instant7);//1970-01-01T00:00:02Z
```

<font color=blue>**3. ZoneDateTime  带时区的时间**</font>

```java
/*
            static ZonedDateTime now() 获取当前时间的ZonedDateTime对象
            static ZonedDateTime ofXxxx(。。。) 获取指定时间的ZonedDateTime对象
            ZonedDateTime withXxx(时间) 修改时间系列的方法
            ZonedDateTime minusXxx(时间) 减少时间系列的方法
            ZonedDateTime plusXxx(时间) 增加时间系列的方法*/
//1.获取当前时间对象(带时区)
ZonedDateTime now = ZonedDateTime.now();
System.out.println(now);

//2.获取指定的时间对象(带时区)1/年月日时分秒纳秒方式指定
ZonedDateTime time1 = ZonedDateTime.of(2023, 10, 1,
                                       11, 12, 12, 0, ZoneId.of("Asia/Shanghai"));
System.out.println(time1);

//通过Instant + 时区的方式指定获取时间对象
Instant instant = Instant.ofEpochMilli(0L);
ZoneId zoneId = ZoneId.of("Asia/Shanghai");
ZonedDateTime time2 = ZonedDateTime.ofInstant(instant, zoneId);
System.out.println(time2);


//3.withXxx 修改时间系列的方法
ZonedDateTime time3 = time2.withYear(2000);
System.out.println(time3);

//4. 减少时间
ZonedDateTime time4 = time3.minusYears(1);
System.out.println(time4);

//5.增加时间
ZonedDateTime time5 = time4.plusYears(1);
System.out.println(time5);
```

<font color=blue>**4. DateTimeFormatter   用于时间的格式化和解析**</font>

```java
/*
            static DateTimeFormatter ofPattern(格式) 获取格式对象
            String format(时间对象) 按照指定方式格式化*/
//获取时间对象
ZonedDateTime time = Instant.now().atZone(ZoneId.of("Asia/Shanghai"));

// 解析/格式化器
DateTimeFormatter dtf1=DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm;ss EE a");
// 格式化
System.out.println(dtf1.format(time));
```

<font color=blue>**5. LocalDate  年、月、日**</font>

```java
//1.获取当前时间的日历对象(包含 年月日)
LocalDate nowDate = LocalDate.now();
//System.out.println("今天的日期:" + nowDate);
//2.获取指定的时间的日历对象
LocalDate ldDate = LocalDate.of(2023, 1, 1);
System.out.println("指定日期:" + ldDate);

System.out.println("=============================");

//3.get系列方法获取日历中的每一个属性值//获取年
int year = ldDate.getYear();
System.out.println("year: " + year);
//获取月//方式一:
Month m = ldDate.getMonth();
System.out.println(m);
System.out.println(m.getValue());

//方式二:
int month = ldDate.getMonthValue();
System.out.println("month: " + month);

//获取日
int day = ldDate.getDayOfMonth();
System.out.println("day:" + day);

//获取一年的第几天
int dayofYear = ldDate.getDayOfYear();
System.out.println("dayOfYear:" + dayofYear);

//获取星期
DayOfWeek dayOfWeek = ldDate.getDayOfWeek();
System.out.println(dayOfWeek);
System.out.println(dayOfWeek.getValue());

//is开头的方法表示判断
System.out.println(ldDate.isBefore(ldDate));
System.out.println(ldDate.isAfter(ldDate));

//with开头的方法表示修改，只能修改年月日
LocalDate withLocalDate = ldDate.withYear(2000);
System.out.println(withLocalDate);

//minus开头的方法表示减少，只能减少年月日
LocalDate minusLocalDate = ldDate.minusYears(1);
System.out.println(minusLocalDate);


//plus开头的方法表示增加，只能增加年月日
LocalDate plusLocalDate = ldDate.plusDays(1);
System.out.println(plusLocalDate);

//-------------
// 判断今天是否是你的生日
LocalDate birDate = LocalDate.of(2000, 1, 1);
LocalDate nowDate1 = LocalDate.now();

MonthDay birMd = MonthDay.of(birDate.getMonthValue(), birDate.getDayOfMonth());
MonthDay nowMd = MonthDay.from(nowDate1);

System.out.println("今天是你的生日吗? " + birMd.equals(nowMd));//今天是你的生日吗?
```

<font color=blue>**6. LocalTime  时、分、秒**</font>

```java
// 获取本地时间的日历对象。(包含 时分秒)
LocalTime nowTime = LocalTime.now();
System.out.println("今天的时间:" + nowTime);

int hour = nowTime.getHour();//时
System.out.println("hour: " + hour);

int minute = nowTime.getMinute();//分
System.out.println("minute: " + minute);

int second = nowTime.getSecond();//秒
System.out.println("second:" + second);

int nano = nowTime.getNano();//纳秒
System.out.println("nano:" + nano);
System.out.println("------------------------------------");
System.out.println(LocalTime.of(8, 20));//时分
System.out.println(LocalTime.of(8, 20, 30));//时分秒
System.out.println(LocalTime.of(8, 20, 30, 150));//时分秒纳秒
LocalTime mTime = LocalTime.of(8, 20, 30, 150);

//is系列的方法
System.out.println(nowTime.isBefore(mTime));
System.out.println(nowTime.isAfter(mTime));

//with系列的方法，只能修改时、分、秒
System.out.println(nowTime.withHour(10));

//plus系列的方法，只能修改时、分、秒
System.out.println(nowTime.plusHours(10));
```

<font color=blue>**7. LocalDateTime  年、月、日、时、分、秒**</font>

```java
// 当前时间的的日历对象(包含年月日时分秒)
LocalDateTime nowDateTime = LocalDateTime.now();

System.out.println("今天是:" + nowDateTime);//今天是：
System.out.println(nowDateTime.getYear());//年
System.out.println(nowDateTime.getMonthValue());//月
System.out.println(nowDateTime.getDayOfMonth());//日
System.out.println(nowDateTime.getHour());//时
System.out.println(nowDateTime.getMinute());//分
System.out.println(nowDateTime.getSecond());//秒
System.out.println(nowDateTime.getNano());//纳秒
// 日:当年的第几天
System.out.println("dayofYear:" + nowDateTime.getDayOfYear());
//星期
System.out.println(nowDateTime.getDayOfWeek());
System.out.println(nowDateTime.getDayOfWeek().getValue());
//月份
System.out.println(nowDateTime.getMonth());
System.out.println(nowDateTime.getMonth().getValue());

LocalDate ld = nowDateTime.toLocalDate();
System.out.println(ld);

LocalTime lt = nowDateTime.toLocalTime();
System.out.println(lt.getHour());
System.out.println(lt.getMinute());
System.out.println(lt.getSecond());
```

<font color=blue>**8. Duration  时间间隔（秒，纳，秒）**</font>

```java
// 本地日期时间对象。
LocalDateTime today = LocalDateTime.now();
System.out.println(today);

// 出生的日期时间对象
LocalDateTime birthDate = LocalDateTime.of(2000, 1, 1, 0, 0, 0);
System.out.println(birthDate);

Duration duration = Duration.between(birthDate, today);//第二个参数减第一个参数
System.out.println("相差的时间间隔对象:" + duration);

System.out.println("============================================");
System.out.println(duration.toDays());//两个时间差的天数
System.out.println(duration.toHours());//两个时间差的小时数
System.out.println(duration.toMinutes());//两个时间差的分钟数
System.out.println(duration.toMillis());//两个时间差的毫秒数
System.out.println(duration.toNanos());//两个时间差的纳秒数
```

<font color=blue>**9. Period  时间间隔（年，月，日)**</font>

```java
// 当前本地 年月日
LocalDate today = LocalDate.now();
System.out.println(today);

// 生日的 年月日
LocalDate birthDate = LocalDate.of(2000, 1, 1);
System.out.println(birthDate);

Period period = Period.between(birthDate, today);//第二个参数减第一个参数

System.out.println("相差的时间间隔对象:" + period);
System.out.println(period.getYears());
System.out.println(period.getMonths());
System.out.println(period.getDays());

System.out.println(period.toTotalMonths());
```

<font color=blue>**10. ChronoUnit  时间间隔（所有单位）**</font>

```java
// 当前时间
LocalDateTime today = LocalDateTime.now();
System.out.println(today);
// 生日时间
LocalDateTime birthDate = LocalDateTime.of(2000, 1, 1,0, 0, 0);
System.out.println(birthDate);

System.out.println("相差的年数:" + ChronoUnit.YEARS.between(birthDate, today));
System.out.println("相差的月数:" + ChronoUnit.MONTHS.between(birthDate, today));
System.out.println("相差的周数:" + ChronoUnit.WEEKS.between(birthDate, today));
System.out.println("相差的天数:" + ChronoUnit.DAYS.between(birthDate, today));
System.out.println("相差的时数:" + ChronoUnit.HOURS.between(birthDate, today));
System.out.println("相差的分数:" + ChronoUnit.MINUTES.between(birthDate, today));
System.out.println("相差的秒数:" + ChronoUnit.SECONDS.between(birthDate, today));
System.out.println("相差的毫秒数:" + ChronoUnit.MILLIS.between(birthDate, today));
System.out.println("相差的微秒数:" + ChronoUnit.MICROS.between(birthDate, today));
System.out.println("相差的纳秒数:" + ChronoUnit.NANOS.between(birthDate, today));
System.out.println("相差的半天数:" + ChronoUnit.HALF_DAYS.between(birthDate, today));
System.out.println("相差的十年数:" + ChronoUnit.DECADES.between(birthDate, today));
System.out.println("相差的世纪(百年)数:" + ChronoUnit.CENTURIES.between(birthDate, today));
System.out.println("相差的千年数:" + ChronoUnit.MILLENNIA.between(birthDate, today));
System.out.println("相差的纪元数:" + ChronoUnit.ERAS.between(birthDate, today));
```

---



## 12 包装类

Java提供了两个类型系统，基本类型与引用类型，使用基本类型在于效率，然而很多情况，会创建对象使用，因为对象可以做更多的功能，如果想要**基本类型像对象一样操作**，就可以使用基本类型对应的包装类：

| 基本类型 | 对应的包装类（位于java.lang包中） |
| -------- | --------------------------------- |
| byte     | Byte                              |
| short    | Short                             |
| int      | **Integer**                       |
| long     | Long                              |
| float    | Float                             |
| double   | Double                            |
| char     | **Character**                     |
| boolean  | Boolean                           |

### 12.1 Integer类

- Integer类：包装一个对象中的原始类型 int 的值

- Integer类构造方法及静态方法

| 方法名                                                   | 说明                                                  |
| -------------------------------------------------------- | ----------------------------------------------------- |
| public Integer(int   value)                              | 根据 int 值创建 Integer 对象(过时)                    |
| public Integer(String s)                                 | 根据 String 值创建 Integer 对象(过时)                 |
| public static Integer **valueOf(int i)**                 | 返回表示指定的 int 值的 Integer   实例                |
| public static Integer **valueOf(String s)**              | 返回保存指定String值的 Integer 对象                   |
| static string tobinarystring(int i)                      | 得到二进制                                            |
| static string tooctalstring(int i)                       | 得到八进制                                            |
| static string toHexstring(int i)                         | 得到十六进制                                          |
| static int <font color=red>**parseInt(string s)**</font> | **强制类型转换**，将字符串类型的整数转成int类型的整数 |

- 示例代码

```java
//public Integer(int value)：根据 int 值创建 Integer 对象(过时)
Integer i1 = new Integer(100);
System.out.println(i1);

//public Integer(String s)：根据 String 值创建 Integer 对象(过时)
Integer i2 = new Integer("100");
//Integer i2 = new Integer("abc"); //NumberFormatException
System.out.println(i2);
System.out.println("--------");

//public static Integer valueOf(int i)：返回表示指定的 int 值的 Integer 实例
Integer i3 = Integer.valueOf(100);
System.out.println(i3);

//public static Integer valueOf(String s)：返回保存指定String值的Integer对象 
Integer i4 = Integer.valueOf("100");
System.out.println(i4);
```

```java
//1.把整数转成二进制，十六进制
String str1 = Integer.toBinaryString(100);
System.out.println(str1);//1100100

//2.把整数转成八进制
String str2 = Integer.toOctalString(100);
System.out.println(str2);//144

//3.把整数转成十六进制
String str3 = Integer.toHexString(100);
System.out.println(str3);//64

//4.将字符串类型的整数转成int类型的整数
//强类型语言:每种数据在java中都有各自的数据类型
//在计算的时候，如果不是同一种数据类型，是无法直接计算的。
int i = Integer.parseInt("123");
System.out.println(i);
System.out.println(i + 1);//124
//细节1:
//在类型转换的时候，括号中的参数只能是数字不能是其他，否则代码会报错
//细节2:
//8种包装类当中，除了Character都有对应的parseXxx的方法，进行类型转换
String str = "true";
boolean b = Boolean.parseBoolean(str);
System.out.println(b);
```

### 12.2 装箱与拆箱

基本类型与对应的包装类对象之间，来回转换的过程称为”装箱“与”拆箱“：

- **装箱**：从基本类型转换为对应的包装类对象。
- **拆箱**：从包装类对象转换为对应的基本类型。

基本数值---->包装对象

```java
Integer i = new Integer(4);//使用构造函数函数
Integer iii = Integer.valueOf(4);//使用包装类中的valueOf方法
```

包装对象---->基本数值

```java
int num = i.intValue();
```

**自动装箱与自动拆箱**

由于经常要做基本类型与包装类之间的转换，从Java 5（JDK 1.5）开始，基本类型与包装类的装箱、拆箱动作可以自动完成。例如：

```java
Integer i = 4;//自动装箱。相当于Integer i = Integer.valueOf(4);
i = i + 5;//等号右边：将i对象转成基本数值(自动拆箱) i.intValue() + 5;
//加法运算完成后，再次装箱，把基本数值转成对象。
```

### 12.3 基本类型与字符串转换

<font color=blue>**1. 基本类型转换为String**</font>

- 转换方式

  - 直接在数字后加一个空字符串

  - 通过String类静态方法valueOf()

- 示例代码

```java
public class IntegerDemo {
    public static void main(String[] args) {
        //int --- String
        int number = 100;
        //方式1
        String s1 = number + "";
        System.out.println(s1);
        //方式2
        //public static String valueOf(int i)
        String s2 = String.valueOf(number);
        System.out.println(s2);
        System.out.println("--------");
    }
}
```

<font color=blue>**2. String转换成基本类型** </font>

除了Character类之外，其他所有包装类都具有parseXxx静态方法可以将字符串参数转换为对应的基本类型：

- `public static byte parseByte(String s)`：将字符串参数转换为对应的byte基本类型。
- `public static short parseShort(String s)`：将字符串参数转换为对应的short基本类型。
- **`public static int parseInt(String s)`：将字符串参数转换为对应的int基本类型。**
- **`public static long parseLong(String s)`：将字符串参数转换为对应的long基本类型。**
- `public static float parseFloat(String s)`：将字符串参数转换为对应的float基本类型。
- `public static double parseDouble(String s)`：将字符串参数转换为对应的double基本类型。
- `public static boolean parseBoolean(String s)`：将字符串参数转换为对应的boolean基本类型。

代码使用（仅以Integer类的静态方法parseXxx为例）如：

- 转换方式
  - 方式一：先将字符串数字转成Integer，再调用valueOf()方法
  - 方式二：通过Integer静态方法parseInt()进行转换
- 示例代码

```java
public class IntegerDemo {
    public static void main(String[] args) {
        //String --- int
        String s = "100";
        //方式1：String --- Integer --- int
        Integer i = Integer.valueOf(s);
        //public int intValue()
        int x = i.intValue();
        System.out.println(x);
        //方式2
        //public static int parseInt(String s)
        int y = Integer.parseInt(s);
        System.out.println(y);
    }
}
```

> 注意:如果字符串参数的内容无法正确转换为对应的基本类型，则会抛`java.lang.NumberFormatException`异常。

<font color=blue>**3. 底层原理** </font>

**建议**：获取Integer对象的时候不要自己new，而是采取直接赋值或者静态方法valueOf的方式

因为在实际开发中，-128~127之间的数据，用的比较多。如果每次使用都是new对象，那么太浪费内存了。

所以，提前把范围内的每一个数据都创建好对象，如果要用到了不会创建新的，而是返回已经创建好的对象。

```java
//1.利用构造方法获取Integer的对象(JDK5以前的方式)
/*Integer i1 = new Integer(1);
        Integer i2 = new Integer("1");
        System.out.println(i1);
        System.out.println(i2);*/

//2.利用静态方法获取Integer的对象(JDK5以前的方式)
Integer i3 = Integer.valueOf(123);
Integer i4 = Integer.valueOf("123");
Integer i5 = Integer.valueOf("123", 8);
System.out.println(i3);
System.out.println(i4);
System.out.println(i5);

//3.这两种方式获取对象的区别(掌握)
//底层原理：
//因为在实际开发中，-128~127之间的数据，用的比较多。
//如果每次使用都是new对象，那么太浪费内存了
//所以，提前把这个范围之内的每一个数据都创建好对象
//如果要用到了不会创建新的，而是返回已经创建好的对象。
Integer i6 = Integer.valueOf(127);
Integer i7 = Integer.valueOf(127);
System.out.println(i6 == i7);//true

Integer i8 = Integer.valueOf(128);
Integer i9 = Integer.valueOf(128);
System.out.println(i8 == i9);//false

//因为看到了new关键字，在Java中，每一次new都是创建了一个新的对象
//所以下面的两个对象都是new出来，地址值不一样。
/*Integer i10 = new Integer(127);
        Integer i11 = new Integer(127);
        System.out.println(i10 == i11);

        Integer i12 = new Integer(128);
        Integer i13 = new Integer(128);
        System.out.println(i12 == i13);*/
```

---



# Java 文件流



## 1 Stream流

### 1.1 Stream流基本使用

<font color=blue>**1. 案例需求** </font>

按照下面的要求完成集合的创建和遍历

- 创建一个集合，存储多个字符串元素
- 把集合中所有以"张"开头的元素存储到一个新的集合
- 把"张"开头的集合中的长度为3的元素存储到一个新的集合
- 遍历上一步得到的集合

<font color=blue>**2. 原始方法示例** </font>

```java
public class MyStream1 {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>(List.of("张三丰","张无忌","张翠山","王二麻子","张良","谢广坤"));

        //遍历list1把以张开头的元素添加到list2中
        ArrayList<String> list2 = new ArrayList<>();
        for (String s : list1) {
            if(s.startsWith("张")){
                list2.add(s);
            }
        }
        //遍历list2集合，把其中长度为3的元素，再添加到list3中
        ArrayList<String> list3 = new ArrayList<>();
        for (String s : list2) {
            if(s.length() == 3){
                list3.add(s);
            }
        }
        for (String s : list3) {
            System.out.println(s);
        }      
    }
}
```

<font color=blue>**3. 使用Stream流示例** </font>

```java
public class StreamDemo {
    public static void main(String[] args) {
        ArrayList<String> list1 = new ArrayList<>(List.of("张三丰","张无忌","张翠山","王二麻子","张良","谢广坤"));

        list1.stream().filter(s->s.startsWith("张"))
                .filter(s->s.length() == 3)
                .forEach(s-> System.out.println(s));
    }
}
```

<font color=blue>**4. Stream流优点** </font>

- 直接阅读代码的字面意思即可完美展示无关逻辑方式的语义：获取流、过滤姓张、过滤长度为3、逐一打印

- Stream流把真正的函数式编程风格引入到Java中

- 代码简洁

  

### 1.2 Stream流常见生成方式

<font color=blue>**1. Stream流的思想** </font>

![01_Stream流思想](javaBasis_assets\01_Stream流思想.png)

<font color=blue>**2. Stream流的三类方法** </font>

- **获取Stream流**：创建一条流水线，并把数据放到流水线上准备进行操作
- **中间方法**：流水线上的操作，一次操作完毕之后，还可以继续进行其他操作

- **终结方法**：一个Stream流只能有一个终结方法，是流水线上的最后一个操作

<font color=blue>**3. 生成Stream流的方式** </font>

- <font color=red>**Collection体系集合**</font>：使用默认方法stream()生成流， default Stream<E> stream()

- <font color=red>**Map体系集合**</font>：把Map转成Set集合，间接的生成流

- <font color=red>**数组**</font>：通过Arrays中的静态方法stream生成流

- <font color=red>**同种数据类型的多个数据**</font>：通过Stream接口的静态方法of(T... values)生成流

  | 获取方式     | 方法名                                        | 说明                     |
  | ------------ | --------------------------------------------- | ------------------------ |
  | 单列集合     | default Stram<E> stream()                     | Collection中的默认方法   |
  | 双列集合     | 无                                            | 无法直接使用stream流     |
  | 数组         | public static <T> Stream<T> stream(T[] array) | Arrays工具类中的静态方法 |
  | 一堆零散数据 | public static <T> Stream <T> of(T ... values) | Stream接口中的静态方法   |

**代码演示**

```java
public class StreamDemo {
    public static void main(String[] args) {
        //1.单列集合获取Stream流
        ArrayList<String> list = new ArrayList<>();
        Collections.addAll(list,"a","b","c","d","e");
        Stream<String> stream1 = list.stream();
        list.stream().forEach(s->System.out.println(s));
        
        //2.双列集合，无法直接使用Stream流，需要借助单列集合转化
        HashMap<String,Integer> hm = new HashMap<>();
        hm.put("aaa",111);
        hm.put("bbb",222);
        hm.put("ccc",333);
        hm.put("ddd",444);
        //第一种方式
        hm.keySet().stream().forEach(s->System.out.println(s)); //先获取所有键，再使用流
        //第二种方式
        hm.entrySet().stream().forEach(s->System.out.println(s));
        
        //3.数组可以通过Arrays中的静态方法stream生成流
        String[] strArray = {"hello","world","java"};
        Arrays.stream(strArray).forEach(s->System.out.println(s));
       
      	//4.同种数据类型的多个数据可以通过Stream接口的静态方法of(T... values)生成流
        Stream.of(1,2,3,4,5).forEach(s->System.out.println(s)); //只要同种就行
        Stream.of("a","b","c","d").forEach(s->System.out.println(s));
        //Stream接口中静态方法of的细节：方法的形参是一个可变参数，可以传递一堆零散的数据，也可以传递数组，但是数组必须是引用数据类型，如果传递基本数据类型，会把整个数组当作一个元素，放到Stream中
    }
}
```



### 1.3 Stream流中间操作方法

- 概念：执行完此方法之后,Stream流依然可以继续执行其他操作

- **常见方法**

  | 方法名                                          | 说明                                 |
  | ----------------------------------------------- | ------------------------------------ |
  | Stream<T> filter(Predicate predicate)           | 过滤                                 |
  | Stream<T> limit(long maxSize)                   | 获取前几个元素                       |
  | Stream<T> skip(long n)                          | 跳过几个元素                         |
  | static <T> Stream<T> concat(Stream a, Stream b) | 合并a和b两个流为一个流               |
  | Stream<T> distinct()                            | 元素去重，依赖(hashcode和equals方法) |
  | Stream<R> map(Function<T,R> mapper)             | 转换流中的数据类型                   |

- 注意：

  - 中间方法，返回新的Stream流，原来的Stream流只使用一次，建议使用<font color=red>**链式编程**</font>

  - 修改Stream流中的数据，不会影响原来集合或数组中的数据

<font color=blue>**1. filter过滤** </font>

```java
public class MyStream {
    public static void main(String[] args) {

        ArrayList<String> list = new ArrayList<>();
        Collections.addAll(list,"张三丰","张无忌","张三","王二","轴心")；
     
        //链式编程示例
        list.stream()
            .filter(s->s.startsWith("张"))
            .filter(s->s.length()==3)
            .forEach(s->System.out.println(s));
    }
}
```

<font color=blue>**2. limit & skip 获取&跳过** </font>

```java
public class StreamDemo02 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();

        list.add("林青霞");
        list.add("张曼玉");
        list.add("王祖贤");
        list.add("柳岩");
        list.add("张敏");
        list.add("张无忌");

        //需求1：取前3个数据在控制台输出
        list.stream().limit(3).forEach(s-> System.out.println(s));

        //需求2：跳过3个元素，把剩下的元素在控制台输出
        list.stream().skip(3).forEach(s-> System.out.println(s));

        //需求3：跳过2个元素，把剩下的元素中前2个在控制台输出
        list.stream().skip(2).limit(2).forEach(s-> System.out.println(s));
    }
} 
```

<font color=blue>**3. concat & distinct 合并&去重** </font>

```java
public class StreamDemo {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();

        list.add("林青霞");
        list.add("张曼玉");
        list.add("王祖贤");
        list.add("柳岩");
        list.add("张敏");
        list.add("张无忌");

        //需求1：取前4个数据组成一个流
        Stream<String> s1 = list.stream().limit(4);

        //需求2：跳过2个数据组成一个流
        Stream<String> s2 = list.stream().skip(2);

        //需求3：合并需求1和需求2得到的流，并把结果在控制台输出
		Stream.concat(s1,s2).forEach(s-> System.out.println(s));

        //需求4：合并需求1和需求2得到的流，并把结果在控制台输出，要求字符串元素不能重复
        Stream.concat(s1,s2).distinct().forEach(s-> System.out.println(s));
    }
}
```

<font color=blue>**4. map转换数据类型** </font>

```java
public class StreamDemo04 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();

        list.add("林青霞-15");
        list.add("张曼玉-23");
        list.add("王祖贤-24");
        list.add("柳岩-18");
        list.add("张敏-78");
        list.add("张无忌-35");

        //需求:只获取里面的年龄并进行打印
        //String -> int
        //匿名内部类写法
        //第一个类型：流中原来的数据类型，第二个类型：要转换之后的数据
        list.stream().map(new Function<String,Integer>(){
            @Override
            public Integer apply(String s){
                String[] arr = s.split("-");
                String ageString = arr[1];
                int age = Integer.parseInt(ageString);
                return age;
            }
        }).forEach(s->System.out.println(s));
        
        //lambda表达式
        list.stream()
            .map(s->Integer.parseInt(s.split("-")[1]))
            .forEach(s->System.out.println(s));
    }
}
```



### 1.4 Stream流终结操作方法

- 概念：终结操作的意思是,执行完此方法之后,Stream流将不能再执行其他操作

- **常见方法**

  | 方法名                        | 说明                           |
  | ----------------------------- | ------------------------------ |
  | void forEach(Consumer action) | 对此流的每个元素执行操作，遍历 |
  | long count()                  | 返回此流中的元素数，统计       |
  | toArray()                     | 收集流中的数据，放到数组中     |
  | collect(Collector collector)  | 收集流中的数据，放到集合中     |

<font color=blue>**1. 遍历和统计** </font>

```java
public class MyStream5 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("张三丰");
        list.add("张无忌");
        list.add("张翠山");
        list.add("王二麻子");
        list.add("张良");
        list.add("谢广坤");
        
        list.stream().forEach(s->System.out.println(s));//遍历
        long count = list.stream().count(); //统计
        System.out.println(count);
    }
}
```

<font color=blue>**2. 收集** </font>

```java
public class MyStream6 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("张三丰");
        list.add("张无忌");
        list.add("张翠山");
        list.add("王二麻子");
        list.add("张良");
        list.add("谢广坤");
        
        //收集流中数据，放到数组中
        Object[] arr1 = list.stream().toArray();
        System.out.println(Arrays.toString(arr1));
        
        //IntFunction的泛型：具体类型的数组
        //apply的形参：流中数据的个数，要跟数组的长度保持一致；apply的返回值：具体类型的数组
        //方法体：创建数组
        //toArray方法参数的作用：负责创建一个指定类型的数组
        //toArray方法的底层：会依次得到流中每一个数据，并把数据放到数组中
        //toArray方法的返回值：是一个装着流里面所有数据的数组
        String[l arr = list.stream().toArray(new IntFunction<String[]>(){
            @Override
            public String[] apply(int value){
                return new String[value];
            }
        });
               
        //简化写法
        String[] arr2 = list.stream().toArray(value->new String[value]);
        System.out.println(Arrays.toString(arr2));       
    }
}
```

工具类Collectors提供了具体的收集方式

| 方法名                                                       | 说明                   |
| ------------------------------------------------------------ | ---------------------- |
| public static <T> Collector toList()                         | 把元素收集到List集合中 |
| public static <T> Collector toSet()                          | 把元素收集到Set集合中  |
| public static  Collector toMap(Function keyMapper,Function valueMapper) | 把元素收集到Map集合中  |

```java
public class MyStream7 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        Collections.addAll(list,"张无忌-男-15","周芷若-女-13","张三-男-23","展望-女-21");
        
        //1.收集到List集合中
        //需求：将所有男性收集起来
        List<String> newList = list.stream()
            .filter(s->"男".equals(s.split("-")[1]))
            .collect(Collectors.toList());
        System.out.println(newList);
        
        //2.收集到Set集合中
        Set<String> newList2 = list.stream()
            .filter(s->"男".equals(s.split("-")[1]))
            .collect(Collectors.toSet());
        System.out.println(newList2); //与list区别：收集到set集合中可以去重
        
        //3.收集到Map集合中
        //注意：要收集到Map集合中，键不能重复，否则会报错
        //键：姓名，值：年龄
        /*toMap:参数一表示键的生成规则，参数二表示值的生成规则
        参数一：
        	Function泛型一：表示流中每一个数据的类型
        		    泛型二：表示Map集合中键的数据类型
        	方法apply形参：依次表示流里面的每一个数据
            		方法体：生成键的代码
            		返回值：已经生成的键
        参数二：
        	Function泛型一：表示流中每一个数据的类型
        		    泛型二：表示Map集合中值的数据类型
        	方法apply形参：依次表示流里面的每一个数据
            		方法体：生成值的代码
            		返回值：已经生成的值*/
        list.stream()
            .filter(s->"男".equals(s.split("-")[1]))
            .collect(Collections.toMap(new Function<String,String>(){
                		@Override
                		public String apply(String s){
                        	return s.split("-")[0];
                		}
            		},
                 new Function<String,Integer(){
                     @Override
                     public Integer apply(String s){
                         return Integer.parseInt(s.split("-")[2]);
                     }
                 }));
        
        //简写版本
        Map<String,Integer> map2 = list.stream()   //ctrl+alt+v 自动生成左边
            .filter(s->"男".equals(s.split("-")[1]))
            .collect(Collectors.toMap(
                s->s.split("-")[0],  //逗号左边是键
                s->Integer.parseInt(s.split("-")[2])));  //右边是值
        System.out.println(map2);
```

###### Stream流综合练习

- 案例需求

  现在有两个ArrayList集合，分别存储6名男演员名称和6名女演员名称，要求完成如下的操作

  - 男演员只要名字为3个字的前三人
  - 女演员只要姓林的，并且不要第一个
  - 把过滤后的男演员姓名和女演员姓名合并到一起
  - 把上一步操作后的元素作为构造方法的参数创建演员对象,遍历数据

  演员类Actor已经提供，里面有一个成员变量，一个带参构造方法，以及成员变量对应的get/set方法

- 代码实现

  演员类

  ```java
  public class Actor {
      private String name;
  
      public Actor(String name) {
          this.name = name;
      }
  
      public String getName() {
          return name;
      }
  
      public void setName(String name) {
          this.name = name;
      }
  }
  ```

  测试类

  ```java
  public class StreamTest {
      public static void main(String[] args) {
          //创建集合
          ArrayList<String> manList = new ArrayList<String>();
          manList.add("周润发");
          manList.add("成龙");
          manList.add("刘德华");
          manList.add("吴京");
          manList.add("周星驰");
          manList.add("李连杰");
    
          ArrayList<String> womanList = new ArrayList<String>();
          womanList.add("林心如");
          womanList.add("张曼玉");
          womanList.add("林青霞");
          womanList.add("柳岩");
          womanList.add("林志玲");
          womanList.add("王祖贤");
    
          //男演员只要名字为3个字的前三人
          Stream<String> manStream = manList.stream().filter(s -> s.length() == 3).limit(3);
    
          //女演员只要姓林的，并且不要第一个
          Stream<String> womanStream = womanList.stream().filter(s -> s.startsWith("林")).skip(1);
    
          //把过滤后的男演员姓名和女演员姓名合并到一起
          Stream<String> stream = Stream.concat(manStream, womanStream);
    
        	// 将流中的数据封装成Actor对象之后打印
        	stream.forEach(name -> {
              Actor actor = new Actor(name);
              System.out.println(actor);
          }); 
      }
  }
  ```

---



## 2 方法引用

### 2.1 方法引用的概念

<font color=blue>**1. 方法引用** </font>：把已有的方法拿过来用，<font color=red>**当作函数式接口中抽象方法的方法体**</font>

<font color=blue>**2. 使用方法引用的条件** </font>

- 引用处必须是**函数接口**

- 被引用的方法必须已经存在

- 被引用的方法的**形参和返回值**需要跟抽象方法保持一致

- 被引用的方法的功能需要满足当前要求

<font color=blue>**3. 方法引用符** </font>

<font color=red>**::**</font>  该符号为引用运算符，而它所在的表达式被称为方法引用

<font color=blue>**4. 推导与省略** </font>

- 若使用Lambda，根据”可推导就是可省略“原则，无需指定参数类型，也无需指定重载形式，都会被自动推导
- 如果使用方法引用，同样可以根据上下文进行推导
- **方法引用是lambda的孪生兄弟**

**代码演示：**

```java
//需求：创建一个数组，进行倒序排列
Integer[] arr = {3,5,4,1,6,2};

//匿名内部类
Arrays.sort(arr,new Comparator<Integer>(){
    @Override
    public int compare(Integer o1,Integer o2){
        return o2-o1;
    }
});

//lambda表达式
//因为第二个参数的类型Comparator是一个函数式接口
Arrays.sort(arr,(Integer o1,Integer o2)->{
    return o2-o1;
});

//lambda简化形式
Arrays.sort(arr,(o1-o2)->o2-o1);

//方法引用
//表示引用FunctionDemo类里面的subtraction方法，将这个方法当作抽象方法的方法体
Arrays.sort(arr,FunctionDemo::subtraction);

//可以是java写好的，也可以是一些第三方工具类
public static int subtraction(int num1,int num2){
    return num2-num1;
}
```

<font color=blue>**5. 方法引用的分类** </font>

- 引用静态方法

- 引用成员方法

  - 引用其他类的成员方法
  - 引用本类的成员方法
  - 引用父类的成员方法

- 引用构造方法

- 其他调用方式

  - 使用类名引用成员方法

  - 引用数组的构造方法

    

### 2.2 引用类方法

类方法：即**静态方法**

<font color=blue>**1. 格式** </font>

```java
类名::静态方法

//举例：Integer::parseInt (Integer类的静态方法)
```

<font color=blue>**2. 代码示例** </font>

```java
//需求：将集合中的以下数字变为int类型："1","2","3","4","5"
//1.创建集合并添加元素
ArrayList<String> list = new ArrayList<>();
Collections.addAll(list,"1","2","3","4","5");

//2.将其变为int类型
list.stream.map(new Function<String,Integer>(){
    @Override
    public Integer apply(String s){
        int i =Integer,parseInt(s);
        return i;
    }
}).forEach(s->System.out.println(s));

//方法引用
list.stream.map(Integer::parseInt).forEach(s->System.out.println(s));
```

==说明==：Lambda表达式被类方法替代的时候，它的形式参数全部传递给静态方法作为参数



### 2.3 引用实例方法

<font color=blue>**1. 引用对象的实例方法(即类中成员方法)** </font>

- **格式**：注意要<font color=red>**new对象**</font>

  ```java
  对象::成员方法
      
  其他类：其他类对象::方法名
  本类：this::方法名	(引用处不能是静态方法)
  父类：super::方法名   (引用处不能是静态方法)
  ```

- **代码演示**

  ```java
  //需求：过滤以张开头，并且名字是3个字的
  
  //1.创建集合 
  ArrayList<String> list = new ArrayList<>();
  Collections.addAll(list,"张无忌","周芷若","赵敏","张强","张三丰");
  //2.过滤数据
  list.stream().filter(s->s.startsWith("张")).filter(s->s.length()==3).forEach(s->System.out.println(s));
  //用方法引用
  list.stream().filter(new StringOperation()::stringJudege)
      .forEach(s->System.out.println(s));
  
  public class StringOperation{
      public boolean stringJudge(String s){
          retrun s.startsWith('张')&&s.length()==3;
      }
  }
  ```

- **练习描述**

  - 定义一个类(PrintString)，里面定义一个方法

    public void printUpper(String s)：把字符串参数变成大写的数据，然后在控制台输出

  - 定义一个接口(Printer)，里面定义一个抽象方法

    void printUpperCase(String s)

  - 定义一个测试类(PrinterDemo)，在测试类中提供两个方法

    - 一个方法是：usePrinter(Printer p)
    - 一个方法是主方法，在主方法中调用usePrinter方法

  ```java
  public class PrintString {
      //把字符串参数变成大写的数据，然后在控制台输出
      public void printUpper(String s) {
          String result = s.toUpperCase();
          System.out.println(result);
      }
  }
  
  public interface Printer {
      void printUpperCase(String s);
  }
  
  public class PrinterDemo {
      public static void main(String[] args) {
  
  		//Lambda简化写法
          usePrinter(s -> System.out.println(s.toUpperCase()));
  
          //引用对象的实例方法
          PrintString ps = new PrintString();
          usePrinter(ps::printUpper);
  
      }
  
      private static void usePrinter(Printer p) {
          p.printUpperCase("HelloWorld");
      }
  }
  ```

- ==说明==：Lambda表达式被对象的实例方法替代的时候，它的形式参数全部传递给该方法作为参数

<font color=blue>**2. 引用类的实例方法(即类中成员方法)** </font>

- **格式**

  ```java
  类名::成员方法
  
  //范例：String::substring  
  ```

- **练习描述**

  - 定义一个接口(MyString)，里面定义一个抽象方法：

    String mySubString(String s,int x,int y);

  - 定义一个测试类(MyStringDemo)，在测试类中提供两个方法

    - 一个方法是：useMyString(MyString my)
    - 一个方法是主方法，在主方法中调用useMyString方法

  ```java
  public interface MyString {
      String mySubString(String s,int x,int y);
  }
  
  public class MyStringDemo {
      public static void main(String[] args) {
  		//Lambda简化写法
          useMyString((s,x,y) -> s.substring(x,y));
  
          //引用类的实例方法
          useMyString(String::substring);
      }
  
      private static void useMyString(MyString my) {
          String s = my.mySubString("HelloWorld", 2, 5);
          System.out.println(s);
      }
  }
  ```
  
- **代码示例**

  ```java
  //需求：集合里的一些字符串，要求变成大写后进行输出
  ArrayList<String> list = new ArrayList<>();
  Collections.addAll(list,"aaa","bbb","ccc","ddd");
  //变成大写后进行输出
  //String --> String
  list.stream().map(new Function<String,String>(){
      @Override
      public String apply(String s){
          return s.toUpperCase();
      }
  }).forEach(s->System.out.println(s));
  
  //方法引用
  list.stream().map(String::toUpperCase).forEach(s->System.out.println(s));
  
  //抽象方法形参的详解：
  //第一个参数：表示被引用的调用者，决定了可以引用哪些类中的方法
  //			在Stream流中，第一个参数一般都表示流里面的每一个数据
  //			假设流里面的数据是字符串，那么使用这种方式进行方法引用，只能引用String这个类的方法
  
  //第二个参数到最后一个参数：跟被引用方法的形参保持一致，如果没有第二个参数，说明被引用的方法需要是无参的成员方法
  
  //简单理解：拿着流里面的每一个数据，去调用String类中的toUpperCase方法，方法的返回值就是转换后的结果
  
  //局限性：不能引用所有类中的成员方法，是跟抽象方法的第一个参数有关，这个参数是什么类型的，那么就只能引用这个类中的方法
  ```

- ==使用说明==：

  ​    Lambda表达式被类的实例方法替代的时候
  ​    第一个参数作为调用者
  ​    后面的参数全部传递给该方法作为参数
  
  

### 2.4 引用构造方法

- **格式**

  ```java
  类名::new
  
  //范例：Student::new 
  ```

- **练习描述**

  - 定义一个类(Student)，里面有两个成员变量(name,age)

    并提供无参构造方法和带参构造方法，以及成员变量对应的get和set方法

  - 定义一个接口(StudentBuilder)，里面定义一个抽象方法

    Student build(String name,int age);

  - 定义一个测试类(StudentDemo)，在测试类中提供两个方法

    - 一个方法是：useStudentBuilder(StudentBuilder s)
    - 一个方法是主方法，在主方法中调用useStudentBuilder方法

- **代码演示**

  ```java
  public class Student {
      private String name;
      private int age;
  
      public Student() {}
      public Student(String name, int age) {this.name = name;this.age = age;}
      public String getName() {return name;}
  	public void setName(String name) {this.name = name;}
      public int getAge() {return age;}
      public void setAge(int age) {this.age = age;}
  }
  
  public interface StudentBuilder {
      Student build(String name,int age);
  }
  
  public class StudentDemo {
      public static void main(String[] args) {
  		//Lambda简化写法
          useStudentBuilder((name,age) -> new Student(name,age));
          //引用构造器
          useStudentBuilder(Student::new);
      }
  
      private static void useStudentBuilder(StudentBuilder sb) {
          Student s = sb.build("林青霞", 30);
          System.out.println(s.getName() + "," + s.getAge());
      }
  }
  ```

- ==使用说明==：Lambda表达式被构造器替代的时候，它的形式参数全部传递给构造器作为参数

  

### 2.5 引用数组的构造方法

- **格式**

  ```java
  数据类型[]::new
  ```

- **练习**：集合中存储一些整数，收集到数组中

```java
//1.创建集合并添加元素
ArrayList<Integer> list = new ArrayList<>();
Collections.addAll(list,1,2,3,4,5);

//2.收集到数组中
list.stream().toArray(new IntFunction<Integer[]>(){
    @Override
    public Integer[] apply(int value){
        return new Integer[value];
    }
});
//改为方法引用
//细节：数组的类型必须与流中数据的类型保持一致
list.stream().toArray(Integer[]::new);

//3.打印
System.out.println(Arrays.toString(arr));
```

###### 综合练习1

集合中存储一些字符串的数据，比如：张三，23，收集到Student类型的数组当中(使用方法引用完成)

```java
//1.创建集合并添加元素
ArrayList<String> list = new ArrayList<>();
Collections.addAll(list,"周新以，13","淘淘，13","邓伟,18","大海,19");
//2.收集到Student类型数组中(先把字符串变为Student对象，再把Student对象收集起来)
Student[] arr = list.stream()
    				.map(Student::new)  //方法引用Student中的构造方法，将流中数据变为Student对象
    				.toArray(Student[]::new); //方法引用数组的构造方法，将流中数据放到数组中
System.out.println(Arrays.toString(arr));
```

```java
//在Student类中，创建字符串对应的构造方法
public Student(String str){
    String[] arr = str.split(",");
    this.name = arr[0];
    this.age = Integer.parseInt(arr[1]); //要将年龄的字符串类型转换为int类型存储
}
```

###### 综合练习2

创建集合添加学生对象，学生对象属性：name，age，只获取姓名并放到数组当中(使用方法引用完成)

```java
//1.创建集合
ArrayList<Student> list = new ArrayList<>();
list.add(new Student("zxy",22));
list.add(new Student("ywi",25));
list.add(new Student("qio",32));
//2.获取姓名放到数组中
String[] arr= list.stream.map(Student::getName).toArray(String[]::new);
System.out.println(Arrays.toString(arr));
```

方法引用的小技巧：

1.现在有没有方法符合当前需求

2.如果有这样的方法，这个方法是否满足引用的规则

- 静态 		类型::方法名
- 成员方法
- 构造方法          类名::new

---



## 3 异常

### 3.1 异常基本概念

<font color=blue>**1. 异常的概念** </font>

**异常** ：程序在执行过程中，出现的非正常的情况，最终会导致JVM的非正常停止

在Java等面向对象的编程语言中，异常本身是一个类，**产生异常**就是<font color=red>**创建异常对象并抛出了一个异常对象**</font>。Java处理异常的方式是**中断处理**

> 异常指的**并不是语法错误**,语法错了,编译不通过,不会产生字节码文件,根本不能运行

<font color=blue>**2. 异常体系** </font>

**异常机制**：帮助**找到程序中的问题**，异常的根类是`java.lang.Throwable`，其下有两个子类：`java.lang.Error`与`java.lang.Exception`，平常所说的异常指`java.lang.Exception`

- 异常的**根类**：<font color=red>**Throwable体系**</font>

  * <font color=red>**Error**</font>:严重错误Error，无法通过处理的错误，只能<font color=red>**事先避免**</font>，好比绝症。

  * <font color=red>**Exception**</font>:表示异常，异常产生后程序员可以通过代码的方式纠正，使程序继续运行，是<font color=red>**必须要处理**</font>的。好比感冒、阑尾炎。


- **Throwable中的常用方法：**

  | 方法                  | 描述                                                         |
  | --------------------- | ------------------------------------------------------------ |
  | **printStackTrace()** | 打印异常的详细信息（包含了异常的类型,异常的原因,还包括异常出现的位置,在开发和调试阶段,都得使用printStackTrace） |
  | **getMessage()**      | 获取发生异常的原因                                           |
  | toString()            | 获取异常的类型和异常描述信息(不用)                           |

  <font color=red>***出现异常,不要紧张,把异常的简单类名,拷贝到API中去查***</font>

![](javaBasis_assets\简单的异常查看.bmp)

<font color=blue>**3. 异常分类** </font>

- 异常体系的**最上层父类**：<font color=red>**Exception**</font>

  - **编译时期异常**:<font color=red>**checked异常**</font>。没有继承RuntimeException的异常，直接继承于Exception。在编译时期,就会检查,如果没有处理异常,则编译失败。(如日期格式化异常)

  * **运行时期异常**:<font color=red>**runtime异常**</font>。RuntimeException本身和子类。在运行时期,检查异常.在编译时期,运行异常不会编译器检测(不报错)。(如数学异常)


​    ![](javaBasis_assets\异常的分类.png)

<font color=blue>**4. 异常的产生过程解析** </font>

程序会产生一个数组索引越界异常ArrayIndexOfBoundsException。通过图解来解析下异常产生的过程。

 **工具类**

```java
public class ArrayTools {
    // 对给定的数组通过给定的角标获取元素。
    public static int getElement(int[] arr, int index) {
        int element = arr[index];
        return element;
    }
}
```

 **测试类**

```java
public class ExceptionDemo {
    public static void main(String[] args) {
        int[] arr = { 34, 12, 67 };
        intnum = ArrayTools.getElement(arr, 4)
        System.out.println("num=" + num);
        System.out.println("over");
    }
}
```

**上述程序执行过程图解**：

 ![](javaBasis_assets\异常产生过程.png)

<font color=blue>**5. 异常在代码中的两个作用** </font>

- 作用一：用来查询bug的关键参考信息
- 作用二：可以作为方法内部的一种**特殊返回值**，以便<font color=red>**通知调用者底层的执行情况**</font>

<font color=blue>**6. 异常的处理方式** </font>

- **JVM默认的处理方式**
  - 把异常的名称，异常原因及异常出现的位置等信息输出在控制台
  - 程序停止执行，下面的代码不会再执行
- 自己处理：捕获异常try…catch
- 抛出异常



### 3.2 捕获异常try…catch

**捕获异常**：Java中对异常**有针对性**的语句进行捕获，可以对出现的异常进行指定方式的处理

<font color=blue>**1. 捕获异常的语法** </font>

```java
try{
     编写可能会出现异常的代码
}catch(异常类型  e){
     处理异常的代码
     //记录日志/打印异常信息/继续抛出异常
}
```

**try：**该代码块中编写可能产生异常的代码

**catch：**用来进行某种异常的捕获，实现对捕获到的异常进行处理

> 注意:try和catch都不能单独使用,**必须连用**

<font color=blue>**2. 目的** </font>

**当代码异常时，可以让程序继续往下执行**

演示如下：

```java
try {// 当产生异常时，必须有处理方式。要么捕获，要么声明。
    read("b.txt");
} catch (FileNotFoundException e) {
    //try中抛出的是什么异常，在括号中就定义什么异常类型
    System.out.println(e);
}
```

<font color=blue>**3. 多个异常使用捕获又该如何处理？** </font>

- 多个异常分别处理
- 多个异常一次捕获，多次处理
- 多个异常一次捕获一次处理

一般使用**一次捕获多次处理**方式，格式如下：

```java
try{
     编写可能会出现异常的代码
}catch(异常类型A  e){  当try中出现A类型异常,就用该catch来捕获.
     处理异常的代码
     //记录日志/打印异常信息/继续抛出异常
}catch(异常类型B  e){  当try中出现B类型异常,就用该catch来捕获.
     处理异常的代码
     //记录日志/打印异常信息/继续抛出异常
}
```

==注意==:这种异常处理方式，要求多个catch中的异常不能相同，并且若catch中的多个异常之间有子父类异常的关系，那么<font color=red>**子类异常要求在上面的catch处理，父类异常在下面的catch处理**</font>

###### 面试四问

<font color=blue>**1. 如果try中没有遇到问题，怎么执行？** </font>

会把try里面的所有代码全部执行完毕，不会执行catch里面代码

<font color=blue>**2. 如果try中可能会遇到多个问题，怎么执行？** </font>

- 会写多个catch与之对应

- 细节：如果要捕获多个异常，这些异常中如果存在父子关系的话，那么父类一定要写在下面

- JDK7前：不同异常的捕获需要分开书写；

  JDK7后：不同异常若处理方式一致，可以合并书写成**“或者形式|”**

<font color=blue>**3. 如果try中遇到的问题没有被捕获，怎么执行？** </font>

相当于try...catch代码白写了，最终会交给虚拟机进行处理

<font color=blue>**4. 如果try中遇到问题，那么try下面的其他代码还会执行吗？** </font>

下面的代码不会执行，直接跳转到对应的catch中，执行catch中的语句体，但是如果没有对应catch与之匹配，还是会交给虚拟机进行处理



### 3.3 抛出异常throw

**抛出异常**：<font color=red>**写在方法内**</font>，结束方法，手动抛出异常对象，交给调用者，方法中下面的代码不再执行

- 创建一个异常对象。封装一些提示信息(信息可以自己编写)
- 需要将这个异常对象告知给调用者。怎么告知呢？怎么将这个异常对象传递到调用者处呢？通过关键字throw就可以完成。**throw 异常对象**。

<font color=blue>**1. 使用格式** </font>

```
throw new 异常类名(参数);
```

 例如：

```java
throw new NullPointerException("要访问的arr数组不存在");
throw new ArrayIndexOutOfBoundsException("该索引在数组中不存在，已超出范围");
```

<font color=blue>**2. 演示throw的使用** </font>

```java
public class ThrowDemo {
    public static void main(String[] args) {
        int[] arr = {2,4,52,2};
        int index = 4;
        int element = getElement(arr, index);

        System.out.println(element);
        System.out.println("over");
    }
    
    public static int getElement(int[] arr,int index){ 
        if(index<0 || index>arr.length-1){
             /* 判断条件如果满足，当执行完throw抛出异常对象后，方法已经无法继续运算。
             这时就会结束当前方法的执行，并将异常告知给调用者。这时就需要通过异常来解决。 */
             throw new ArrayIndexOutOfBoundsException("哥们，角标越界了```");
        }
        int element = arr[index];
        return element;
    }
}
```

==注意==：如果产生了问题，就会throw将问题描述类即异常进行抛出，也就是<font color=red>**将问题返回给该方法的调用者**</font>。

那么对于调用者来说，该怎么处理呢？

- 一种是<font color=red>**进行捕获处理**</font>

- 另一种就是<font color=red>**继续将问题声明出去**</font>，使用throws声明处理

  

### 3.4 声明异常throws

**声明异常**：<font color=red>**写在方法定义处**</font>，表示声明一个异常，告诉调用者，使用本方法**可能会有哪些异常**

<font color=blue>**1. 使用格式** </font>

```
修饰符 返回值类型 方法名(参数) throws 异常类名1,异常类名2…{   }	
```

编译时异常：必须要写

运行时异常：可以不写

<font color=blue>**2. 代码演示** </font>

```java
public class ThrowsDemo {
    public static void main(String[] args) throws FileNotFoundException {
        read("a.txt");
    }

    // 如果定义功能时有问题发生需要报告给调用者。可以通过在方法上使用throws关键字进行声明
    public static void read(String path) throws FileNotFoundException {
        if (!path.equals("a.txt")) {//如果不是 a.txt这个文件 
            // 我假设  如果不是 a.txt 认为 该文件不存在 是一个错误 也就是异常  throw
            throw new FileNotFoundException("文件不存在");
        }
    }
}
```

throws用于进行异常类的声明，若该方法可能有多种异常情况产生，那么在throws后面可以写多个异常类，用<font color=red>**逗号隔开**</font>。

```java
public class ThrowsDemo2 {
    public static void main(String[] args) throws IOException {
        read("a.txt");
    }

    public static void read(String path)throws FileNotFoundException, IOException {
        if (!path.equals("a.txt")) {//如果不是 a.txt这个文件 
            // 我假设  如果不是 a.txt 认为 该文件不存在 是一个错误 也就是异常  throw
            throw new FileNotFoundException("文件不存在");
        }
        if (!path.equals("b.txt")) {
            throw new IOException();
        }
    }
}
```



### 3.5 finally 代码块

**finally**：有一些特定的代码无论异常是否发生，都需要执行。另外，因为异常会引发程序跳转，导致有些语句执行不到。而finally就是解决这个问题的，<font color=red>**在finally代码块中存放的代码都是一定会被执行的**</font>。

<font color=blue>**1. 什么时候的代码必须最终执行？** </font>

在try语句块中打开了一些物理资源(磁盘文件/网络连接/数据库连接等),都得在使用完之后,**最终关闭打开的资源**。

<font color=blue>**2. finally语法** </font>

 try...catch....finally:自身需要处理异常,最终还得关闭资源。

> 注意:finally不能单独使用。

比如在IO流中，当打开了一个关联文件的资源，最后程序不管结果如何，都需要把这个资源关闭掉。

finally代码参考如下：

```java
public class TryCatchDemo {
    public static void main(String[] args) {
        try {
            read("a.txt");
        } catch (FileNotFoundException e) {
            //抓取到的是编译期异常  抛出去的是运行期 
            throw new RuntimeException(e);
        } finally {
            System.out.println("不管程序怎样，这里都将会被执行。");
        }
        System.out.println("over");
    }
    /*当前的这个方法中 有异常  有编译期异常*/
    public static void read(String path) throws FileNotFoundException {
        if (!path.equals("a.txt")) {//如果不是 a.txt这个文件 
            // 我假设  如果不是 a.txt 认为 该文件不存在 是一个错误 也就是异常  throw
            throw new FileNotFoundException("文件不存在");
        }
    }
}
```

> 当**只有在try或者catch中调用退出JVM的相关方法,此时finally才不会执行**,否则finally永远会执行。

==注意事项==

* 运行时异常被抛出可以不处理。即不捕获也不声明抛出。

* 如果父类抛出了多个异常,子类覆盖父类方法时,只能抛出相同的异常或者是他的子集。

* 父类方法没有抛出异常，子类覆盖父类该方法时也不可抛出异常。此时子类产生该异常，只能捕获处理，不能声明抛出

* 当多异常处理时，捕获处理，前边的类不能是后边类的父类

* 在try/catch后可以追加finally代码块，其中的代码一定会被执行，通常用于资源回收

  

### 3.6 自定义异常

<font color=blue>**1. 为什么需要自定义异常类** </font>

Java中不同的异常类，分别表示着某一种具体的异常情况，那么在开发中总是有些异常情况是SUN没有定义好的,此时根据自己业务的异常情况来定义异常类。例如年龄负数问题,考试成绩负数问题。

<font color=blue>**2. 什么是自定义异常类** </font>

在开发中根据自己业务的异常情况来定义异常类

自定义一个业务逻辑异常: **LoginException**。一个登陆异常类

<font color=blue>**3. 异常类如何定义** </font>

- 自定义一个编译期异常: 自定义类 并继承于`java.lang.Exception`。
- 自定义一个运行时期的异常类:自定义类 并继承于`java.lang.RuntimeException`。

###### 自定义异常的练习

要求：我们模拟登陆操作，如果用户名已存在，则抛出异常并提示：亲，该用户名已经被注册。

首先定义一个登陆异常类LoginException：

```java
// 业务逻辑异常
public class LoginException extends Exception {
    public LoginException() {}

    /**@param message 表示异常提示*/
    public LoginException(String message) {
        super(message);
    }
}
```

模拟登陆操作，使用数组模拟数据库中存储的数据，并提供当前注册账号是否存在方法用于判断。

```java
public class Demo {
    // 模拟数据库中已存在账号
    private static String[] names = {"bill","hill","jill"};
   
    public static void main(String[] args) {     
        try{
            // 可能出现异常的代码
            checkUsername("nill");
            System.out.println("注册成功");//如果没有异常就是注册成功
        } catch(LoginException e) {
            //处理异常
            e.printStackTrace();
        }
    }

    //判断当前注册账号是否存在
    //因为是编译期异常，又想调用者去处理 所以声明该异常
    public static boolean checkUsername(String uname) throws LoginException {
        for (String name : names) {
            if(name.equals(uname)){//如果名字在这里面 就抛出登陆异常
                throw new LoginException("亲"+name+"已经被注册了！");
            }
        }
        return true;
    }
}
```

---



## 4 File类

### 4.1 File的基本使用

`java.io.File` 类：<font color=red>**文件和目录路径名的抽象表示**</font>，主要用于文件和目录的创建、查找和删除等操作

- File对象表示一个路径，可以是文件路径，也可以是文件夹路径
- 这个路径可以存在，也可以不存在

<font color=blue>**1. 构造方法** </font>

| 方法                              | 描述                                                       |
| --------------------------------- | ---------------------------------------------------------- |
| File(String pathname)             | 将给定的**路径名字符串**转换为抽象路径名来创建新的File实例 |
| File(String parent, String child) | 从**父路径名字符串和子路径名字符串**创建新的File实例       |
| File(File parent, String child)   | 从**父抽象路径名和子路径名字符串**创建新的File实例         |

```java
// 文件路径名
String pathname = "D:\\aaa.txt";
File file1 = new File(pathname); 

// 文件路径名
String pathname2 = "D:\\aaa\\bbb.txt";
File file2 = new File(pathname2); 

// 通过父路径和子路径字符串
 String parent = "d:\\aaa";
 String child = "bbb.txt";
 File file3 = new File(parent, child);

// 通过父级File对象和子路径字符串
File parentDir = new File("d:\\aaa");
String child = "bbb.txt";
File file4 = new File(parentDir, child);
```

> 小贴士：
>
> 1. 一个File对象代表硬盘中实际存在的一个文件或者目录。
> 2. 无论该路径下是否存在文件或者目录，**都不影响File对象的创建**。

<font color=blue>**2. 常用方法** </font>

| 方法                     | 描述                               |
| ------------------------ | ---------------------------------- |
| String getAbsolutePath() | 返回此File的绝对路径名字符串       |
| String getPath()         | 将此File转换为路径名字符串         |
| String getName()         | 返回由此File表示的文件或目录的名称 |
| long length()            | 返回由此File表示的文件的长度       |

```java
public class FileGet {
    public static void main(String[] args) {
        File f = new File("d:/aaa/bbb.java");     
        System.out.println("文件绝对路径:"+f.getAbsolutePath());
        System.out.println("文件构造路径:"+f.getPath());
        System.out.println("文件名称:"+f.getName());
        System.out.println("文件长度:"+f.length()+"字节");

        File f2 = new File("d:/aaa");     
        System.out.println("目录绝对路径:"+f2.getAbsolutePath());
        System.out.println("目录构造路径:"+f2.getPath());
        System.out.println("目录名称:"+f2.getName());
        System.out.println("目录长度:"+f2.length());
    }
}
输出结果：
文件绝对路径:d:\aaa\bbb.java
文件构造路径:d:\aaa\bbb.java
文件名称:bbb.java
文件长度:636字节

目录绝对路径:d:\aaa
目录构造路径:d:\aaa
目录名称:aaa
目录长度:4096
```

> API中说明：length()，表示文件的长度。但是File对象表示目录，则返回值未指定。

<font color=blue>**3. 绝对路径和相对路径** </font>

- **绝对路径**：从盘符开始的路径，这是一个完整的路径。
- **相对路径**：相对于项目目录的路径，这是一个便捷的路径，开发中经常使用。

```java
public class FilePath {
    public static void main(String[] args) {
      	// D盘下的bbb.java文件
        File f = new File("D:\\bbb.java");
        System.out.println(f.getAbsolutePath());
      	
		// 项目下的bbb.java文件
        File f2 = new File("bbb.java");
        System.out.println(f2.getAbsolutePath());
    }
}
输出结果：
D:\bbb.java
D:\idea_project_test4\bbb.java
```

<font color=blue>**4. 判断功能的方法** </font>

| 方法          | 描述                               |
| ------------- | ---------------------------------- |
| exists()      | 此File表示的文件或目录是否实际存在 |
| isDirectory() | 此File表示的是否为目录             |
| isFile()      | 此File表示的是否为文件             |

```java
public class FileIs {
    public static void main(String[] args) {
        File f = new File("d:\\aaa\\bbb.java");
        File f2 = new File("d:\\aaa");
      	// 判断是否存在
        System.out.println("d:\\aaa\\bbb.java 是否存在:"+f.exists());
        System.out.println("d:\\aaa 是否存在:"+f2.exists());
      	// 判断是文件还是目录
        System.out.println("d:\\aaa 文件?:"+f2.isFile());
        System.out.println("d:\\aaa 目录?:"+f2.isDirectory());
    }
}
输出结果：
d:\aaa\bbb.java 是否存在:true
d:\aaa 是否存在:true
d:\aaa 文件?:false
d:\aaa 目录?:true
```

<font color=blue>**5. 创建删除功能的方法** </font>

| 方法            | 描述                                                   |
| --------------- | ------------------------------------------------------ |
| createNewFile() | 当且仅当具有该名称的文件尚不存在时，创建一个新的空文件 |
| delete()        | 删除由此File表示的文件或目录                           |
| mkdir()         | 创建由此File表示的目录                                 |
| mkdirs()        | 创建由此File表示的目录，包括任何必需但不存在的父目录   |

```java
public class FileCreateDelete {
    public static void main(String[] args) throws IOException {
        // 文件的创建
        File f = new File("aaa.txt");
        System.out.println("是否存在:"+f.exists()); // false
        System.out.println("是否创建:"+f.createNewFile()); // true
        System.out.println("是否存在:"+f.exists()); // true
		
     	// 目录的创建
      	File f2= new File("newDir");	
        System.out.println("是否存在:"+f2.exists());// false
        System.out.println("是否创建:"+f2.mkdir());	// true
        System.out.println("是否存在:"+f2.exists());// true

		// 创建多级目录
      	File f3= new File("newDira\\newDirb");
        System.out.println(f3.mkdir());// false
        File f4= new File("newDira\\newDirb");
        System.out.println(f4.mkdirs());// true
      
      	// 文件的删除
       	System.out.println(f.delete());// true
      
      	// 目录的删除
        System.out.println(f2.delete());// true
        System.out.println(f4.delete());// false
    }
}
```

> API中说明：delete方法，如果此File表示目录，则目录必须为空才能删除。

<font color=blue>**6. 目录的遍历** </font>

| 方法               | 描述                                                   |
| ------------------ | ------------------------------------------------------ |
| String[] list()    | 返回一个String数组，表示该File目录中的所有子文件或目录 |
| File[] listFiles() | 返回一个File数组，表示该File目录中的所有的子文件或目录 |

```java
public class FileFor {
    public static void main(String[] args) {
        File dir = new File("d:\\java_code");
      
      	//获取当前目录下的文件以及文件夹的名称。
		String[] names = dir.list();
		for(String name : names){
			System.out.println(name);
		}
        //获取当前目录下的文件以及文件夹对象，只要拿到了文件对象，那么就可以获取更多信息
        File[] files = dir.listFiles();
        for (File file : files) {
            System.out.println(file);
        }
    }
}
```

> 小贴士：调用listFiles方法的File对象，表示的必须是实际存在的目录，否则返回null，无法进行遍历。
>



### 4.2 File的综合练习

<font color=blue>**1. 创建文件夹** </font>

在当前模块下的aaa文件夹中创建一个a.txt文件

```java
public class Test1 {
    public static void main(String[] args) throws IOException {
        //1.创建a.txt的父级路径
        File file = new File("myfile\\aaa");
        //2.创建父级路径
        //如果aaa是存在的，那么此时创建失败的。
        //如果aaa是不存在的，那么此时创建成功的。
        file.mkdirs();
        //3.拼接父级路径和子级路径
        File src = new File(file,"a.txt");
        boolean b = src.createNewFile();
        if(b){
            System.out.println("创建成功");
        }else{
            System.out.println("创建失败");
        }
    }
}
```

<font color=blue>**2. 查找文件（不考虑子文件夹）** </font>

定义一个方法找某一个文件夹中，是否有以avi结尾的电影（暂时不需要考虑子文件夹）

```java
public class Test2 {
    public static void main(String[] args) {
        File file = new File("D:\\aaa\\bbb");
        boolean b = haveAVI(file);
        System.out.println(b);
    }
    /*作用：用来找某一个文件夹中，是否有以avi结尾的电影
    * 形参：要查找的文件夹
    * 返回值：查找的结果  存在true  不存在false*/
    public static boolean haveAVI(File file){// D:\\aaa
        //1.进入aaa文件夹，而且要获取里面所有的内容
        File[] files = file.listFiles();
        //2.遍历数组获取里面的每一个元素
        for (File f : files) {
            //f：依次表示aaa文件夹里面每一个文件或者文件夹的路径
            if(f.isFile() && f.getName().endsWith(".avi")){
                return true;
            }
        }
        //3.如果循环结束之后还没有找到，直接返回false
        return false;
    }
}
```

<font color=blue>**3. 查找文件（考虑子文件夹）** </font>

找到电脑中所有以avi结尾的电影。（需要考虑子文件夹）

```java
public class Test3 {
    public static void main(String[] args) {
        /* 套路：
            1，进入文件夹
            2，遍历数组
            3，判断
            4，判断*/
        findAVI();
    }

    public static void findAVI(){
        //获取本地所有的盘符
        File[] arr = File.listRoots();
        for (File f : arr) {
            findAVI(f);
        }
    }

    public static void findAVI(File src){//"C:\\
        //1.进入文件夹src
        File[] files = src.listFiles();
        //2.遍历数组,依次得到src里面每一个文件或者文件夹
        if(files != null){
            for (File file : files) {
                if(file.isFile()){
                    //3，判断，如果是文件，就可以执行题目的业务逻辑
                    String name = file.getName();
                    if(name.endsWith(".avi")){
                        System.out.println(file);
                    }
                }else{
                    //4，判断，如果是文件夹，就可以递归
                    //细节：再次调用本方法的时候，参数一定要是src的次一级路径
                    findAVI(file);
                }
            }
        }
    }
}
```

<font color=blue>**4. 删除多级文件夹** </font>

需求： 如果我们要删除一个有内容的文件夹
	   1.先删除文件夹里面所有的内容
           2.再删除自己

```java
public class Test4 {
    public static void main(String[] args) {
        File file = new File("D:\\aaa\\src");
        delete(file);
    }

    /*作用：删除src文件夹
    * 参数：要删除的文件夹*/
    public static void delete(File src){
        //1.先删除文件夹里面所有的内容
        //进入src
        File[] files = src.listFiles();
        //遍历
        for (File file : files) {
            //判断,如果是文件，删除
            if(file.isFile()){
                file.delete();
            }else {
                //判断,如果是文件夹，就递归
                delete(file);
            }
        }
        //2.再删除自己
        src.delete();
    }
}
```

<font color=blue>**5. 统计大小** </font>

需求：统计一个文件夹的总大小

```java
public class Test5 {
    public static void main(String[] args) {
        File file = new File("D:\\aaa\\src");
        long len = getLen(file);
        System.out.println(len);//4919189
    }

    /*作用：统计一个文件夹的总大小
    * 参数：表示要统计的那个文件夹
    * 返回值：统计之后的结果
    * 文件夹的总大小：说白了，文件夹里面所有文件的大小*/
    public static long getLen(File src){
        //1.定义变量进行累加
        long len = 0;
        //2.进入src文件夹
        File[] files = src.listFiles();
        //3.遍历数组
        for (File file : files) {
            //4.判断
            if(file.isFile()){
                //我们就把当前文件的大小累加到len当中
                len = len + file.length();
            }else{
                //判断，如果是文件夹就递归
                len = len + getLen(file);
            }
        }
        return len;
    }
}
```

<font color=blue>**6. 统计文件个数** </font>

  需求：统计一个文件夹中每种文件的个数并打印。（考虑子文件夹）
            打印格式如下：
            txt:3个
            doc:4个
            jpg:6个

```java
public class Test6 {
    public static void main(String[] args) throws IOException {
        File file = new File("D:\\aaa\\src");
        HashMap<String, Integer> hm = getCount(file);
        System.out.println(hm);
    }

    /*作用：统计一个文件夹中每种文件的个数
    * 参数：要统计的那个文件夹
    * 返回值：用来统计map集合
    *       键：后缀名 值：次数
    *       a.txt
    *       a.a.txt
    *       aaa（不需要统计的）*/
    public static HashMap<String,Integer> getCount(File src){
        //1.定义集合用来统计
        HashMap<String,Integer> hm = new HashMap<>();
        //2.进入src文件夹
        File[] files = src.listFiles();
        //3.遍历数组
        for (File file : files) {
            //4.判断，如果是文件，统计
            if(file.isFile()){
                //a.txt
                String name = file.getName();
                String[] arr = name.split("\\.");
                if(arr.length >= 2){
                    String endName = arr[arr.length - 1];
                    if(hm.containsKey(endName)){
                        //存在
                        int count = hm.get(endName);
                        count++;
                        hm.put(endName,count);
                    }else{
                        //不存在
                        hm.put(endName,1);
                    }
                }
            }else{
                //5.判断，如果是文件夹，递归
                //sonMap里面是子文件中每一种文件的个数
                HashMap<String, Integer> sonMap = getCount(file);
                //hm:  txt=1  jpg=2  doc=3
                //sonMap: txt=3 jpg=1
                //遍历sonMap把里面的值累加到hm当中
                Set<Map.Entry<String, Integer>> entries = sonMap.entrySet();
                for (Map.Entry<String, Integer> entry : entries) {
                    String key = entry.getKey();
                    int value = entry.getValue();
                    if(hm.containsKey(key)){
                        //存在
                        int count = hm.get(key);
                        count = count + value;
                        hm.put(key,count);
                    }else{
                        //不存在
                        hm.put(key,value);
                    }
                }
            }
        }
        return hm;
    }
}
```

---



## 5 IO基本流

### 5.1 IO流的基本概念

<font color=blue>**1. IO流基本概念** </font>

- **IO流**：存储和读取数据的解决方案；用于**读取文件中的数据**
- **File**：系统中的文件/文件夹路径；File类只能**对文件本身进行操作**，不能读写文件中存储的数据
- **I/O操作**:使用`java.io`包下的内容，进行输入、输出操作。<font color=red>**输入**</font>也叫做<font color=red>**读取**</font>数据，<font color=red>**输出**</font>也叫做作<font color=red>**写出**</font>数据

<font color=blue>**2. IO流的分类** </font>

![image-20240706161622321](javaBasis_assets\IO流分类.png)

**纯文本文件**：Windows自带的记事本可以读懂的文件。word和excel就不算纯文本文件

<font color=blue>**3. 顶级父类们** </font>

|            |           **输入流**            |              输出流              |
| :--------: | :-----------------------------: | :------------------------------: |
| **字节流** | 字节输入流<br />**InputStream** | 字节输出流<br />**OutputStream** |
| **字符流** |   字符输入流<br />**Reader**    |    字符输出流<br />**Writer**    |



### 5.2 字节流

#### 5.2.1 字节输出流

`java.io.OutputStream `抽象类是表示字节输出流的所有类的超类，将指定的字节信息写出到目的地

<font color=blue>**1. 主要方法** </font>

| 方法                                                         | 作用                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| FileOutputStream fos = new FileOutputStream("zxy\\a.txt")    | 使用文件名创建流对象                                         |
| File file = new File("a.txt");<br/>FileOutputStream fos = new FileOutputStream(file); | 使用File对象创建流对象                                       |
| fos.write(97);                                               | 一次写出一个字节数据                                         |
| public void write(byte[] b, int off, int len)                | 从指定的字节数组写入 len字节，从偏移量 off开始输出到此输出流 |
| public void write(byte[] b)                                  | 将 b.length字节从指定的字节数组写入此输出流                  |
| public abstract void write(int b)                            |                                                              |
| public void flush()                                          | 刷新此输出流并强制任何缓冲的输出字节被写出                   |
| fos.close();                                                 | 释放资源，每次使用完流后都会释放资源                         |

<font color=blue>**2. 创建字节输出流对象** </font>

- **细节1**：参数是字符串表示的路径或是File对象都可以
- **细节2**：若文件不存在会创建一个新的文件，但是要保证父级路径存在
- **细节3**：若文件已经存在，则<font color=red>**会清空文件**</font>

==注意==：write方法的参数是整数，但实际上写到本地文件上的是整数在ASCII上对应的字符

**写出字节数据示例**

```java
public class FOSWrite {
    public static void main(String[] args) throws IOException {
        FileOutputStream fos = new FileOutputStream("fos.txt");  
        
        //1.一次写一个字节
        fos.write(97);  //a
        //2.一次写一个数组
        byte[] bytes = {97,98,99,100,101};
        fos.write(bytes);
        //3.一次写一个字节数组的一部分
        //参数1：数组，参数2：起始索引，参数3：个数
        fos.write(bytes,1,2); //98，99
        
      	// 字符串转换为字节数组
      	byte[] b = "黑马程序员".getBytes();
      	// 写出字节数组数据
      	fos.write(b);
        
      	// 关闭资源
        fos.close();
    }
}
```

<font color=blue>**3. 写出字节数组的两种特殊情况** </font>

```java
FileOutputStream fos = new FileOutputStream("fos.txt");

/*换行写：
	再次写出一个换行符
	Windows：\r\n
	Linux: 	\n
	Mac:   	\r
	在Windows操作系统中，java进行优化，写其中一个\r,\n均可实现换行，java在底层进行了补全
 续写：	
	打开续写开关,在创建对象的第二个参数
	public FileOutputStream(File file,boolean append),定义了续写开关
	FileOutputStream fos = new FileOutputStream("fos.txt",true);手动定义true即可*/

//换行写
String str = "zhouxinyihaomei";
byte[] bytes1 = str.getBytes();
fos.write(bytes1);

String wrap = "\r\n";
byte[] bytes2 = wrap.getBytes();
fos.write(bytes2);

String str2 = "666";
byte[] bytes3 = str2.getBytes();
fos.write(bytes3);
```

#### 5.2.2 字节输入流

`java.io.InputStream`抽象类是表示字节输入流的所有类的超类，将本地文件中的数据读取到程序中

<font color=blue>**1. 主要方法** </font>

| 方法                                                         | 作用                                         |
| ------------------------------------------------------------ | -------------------------------------------- |
| FileInputStream fis = new FileInputStream("b.txt");          | 使用文件名称创建流对象，即从这个文件中读取   |
| File file = new File("a.txt");<br/>FileInputStream fos = new FileInputStream(file); | 使用File对象创建流对象                       |
| int b1 = fis.read();                                         | 读取数据                                     |
| fis.close();                                                 | 关闭此输入流并释放与此流相关联的任何系统资源 |

<font color=blue>**2. 创建字节输入流对象** </font>

**读取字节**：一个个的读取，当读到文件最后读不到了，则会返回-1

```java
public class FISRead {
    public static void main(String[] args) throws IOException{
       	FileInputStream fis = new FileInputStream("read.txt");

        int read = fis.read();
        System.out.println((char) read);
        read = fis.read();
        System.out.println((char) read);
        read = fis.read();
        System.out.println((char) read);
        read = fis.read();
        System.out.println((char) read);
        read = fis.read();
        System.out.println((char) read);
      	// 读取到末尾,返回-1
       	read = fis.read();
        System.out.println( read);

        fis.close();
    }
}
```

<font color=blue>**3. 字节输入流循环读取** </font>

```java
public class FISRead {
    public static void main(String[] args) throws IOException{
       	FileInputStream fis = new FileInputStream("read.txt");
        int b ；
        while ((b = fis.read())!=-1) {
            System.out.println((char)b);
        }
        
        /*while((fis.read()!=-1)){
        	System.out.println(fis.read());
        }  //运行错误，因为read表示读取一次数据，便移动一次指针，此时有两个read，便移动两次，出现数值丢失。所以循环读取时，必须重新定义第三方变量*/
        fis.close();
    }
}
```

<font color=blue>**4. 字节数组读取** </font>

`read(byte[] b)`，每次读取b的长度个字节到数组中，返回读取到的有效字节个数，读取到末尾时，返回`-1` 

注意：一次读取一个字节数组的数据，每次读取会尽可能把数组装满，一般用**1024的整数倍**

```java
public class FISRead {
    public static void main(String[] args) throws IOException{
       	FileInputStream fis = new FileInputStream("read.txt"); // 文件中为abcde
      	// 定义变量，作为有效个数
        int len ；
        // 定义字节数组，作为装字节数据的容器   
        byte[] b = new byte[2];
        // 循环读取
        while (( len = fis.read(b))!=-1) {
           	// 每次读取后,把数组变成字符串打印
            System.out.println(new String(b));
        }
        fis.close();
    }
}

输出结果：
ab
cd
ed 
```

![image-20240706183605371](javaBasis_assets\一次写多个字节.png)

错误数据`d`，是由于最后一次读取时，只读取一个字节`e`，数组中，上次读取的数据没有被完全替换，所以要通过`len` ，获取有效的字节，代码使用演示：

```java
public class FISRead {
    public static void main(String[] args) throws IOException{
       	FileInputStream fis = new FileInputStream("read.txt"); // 文件中为abcde
        int len ； 
        byte[] b = new byte[2];
        while (( len= fis.read(b))!=-1) {
           	// 每次读取后,把数组的有效字节部分，变成字符串打印
            System.out.println(new String(b，0，len));//  len 每次读取的有效字节个数
            //这种情况下，最后len=1，则为0到1索引，最后输出为e
        }
        fis.close();
    }
}

输出结果：
ab
cd
e
```

> 小贴士：使用数组读取，每次读取多个字节，减少系统间的IO操作次数，从而提高读写的效率，建议开发中使用

- 注意点
  - 输入流，若文件不存在，直接报错
  - 输出流，若文件不存在，创建
  - 读取数据：一次读一个字节，读出来的数据是ASCII上对应的数字，读到文件末尾，read方法返回-1

#### 5.2.3 文件拷贝

**复制原理图解**

![](javaBasis_assets\2_copy.jpg)

复制图片文件，代码使用演示：

```java
public class Copy {
    public static void main(String[] args) throws IOException {
        // 1.创建对象
        FileInputStream fis = new FileInputStream("D:\\test.jpg");   //指定数据源
        FileOutputStream fos = new FileOutputStream("test_copy.jpg");//指定目的地

        // 2.拷贝 - 边读边写
        byte[] b = new byte[1024]; //根据内存选择1024*1024*5
        int len;
        while ((len = fis.read(b))!=-1) {
            fos.write(b, 0 , len);
        }
        
        //3.释放资源
        fos.close();
        fis.close();
    }
}
```

> 小贴士：流的关闭原则：**先开后关，后开先关**。



### 5.3 字符流

当使用字节流读取文本文件时，可能会遇到<font color=red>**中文字符**</font>时，不会显示完整的字符，那是因为一个中文字符可能占用多个字节存储。所以Java提供一些字符流类，以字符为单位读写数据，专门用于处理文本文件。

#### 5.3.1 字符集

计算机的存储规则：在计算机中，任意数据都是以二进制的形式存储的，字节是计算机中最小的存储单元

<font color=blue>**1. ASCII字符集** </font>

计算机在存储**英文**时，一个字节足以

ASCII编码规则：**前面补0，补齐8位**

<img src="javaBasis_assets\ascii存储.png" alt="image-20240706190505522" style="zoom: 33%;" />

ASCII解码规则：**直接转成十进制**

<font color=blue>**2. GBK字符集** </font>

2000年3月17日发布，windows默认使用的是GBK，**系统显示：ANSI**

英文存储：与ASCII字符集规则一致

中文存储：

<img src="javaBasis_assets\GBK存储.png" alt="image-20240706191827150" style="zoom: 33%;" />

因为英文一定是以0开头，中文一定是以1开头，底层二进制文件便用0和1区分彼此

<font color=blue>**3. Unicode字符集** </font>

万国码，国际标准字符集，将世界各种语言的每个字符定义一个唯一的编码

<img src="javaBasis_assets\unicode英文.png" style="zoom: 33%;" />

<img src="javaBasis_assets\unicode中.png" alt="image-20240706192625881" style="zoom:33%;" />

转换方案：

<img src="javaBasis_assets\unicode转换.png" alt="image-20240706192724489" style="zoom: 33%;" />

UTF-8不是字符集，它是一种编码方式（实际开发中使用）

<font color=blue>**4. 为什么会乱码？** </font>

- 原因1：读取数据时未读完整个汉字

  - 字节流一次读取一个字节

- 原因2：**编码和解码时的方式不统一**

  ![image-20240706193426509](javaBasis_assets\乱码.png)

<font color=blue>**5. 解决乱码问题** </font>

- 不要用字节流读取文本文件
- 编码解码时使用同一个码表，同一个编码方式

==疑问：字节流读取中文会乱码，但为什么拷贝不会出现乱码？==

因为数据源和目的地编码方式一致

<font color=blue>**6. java中编解码方式** </font>

| String类中的方法                            | 说明                 |
| ------------------------------------------- | -------------------- |
| Java中编码方式：                            |                      |
| byte[] getBytes()                           | 使用默认方式进行编码 |
| byte[] **getBytes(String charsetName)**     | 使用指定方式进行编码 |
| Java中解码方式：                            |                      |
| String(byte[] bytes)                        | 使用默认方式进行解码 |
| **String(byte[] bytes,String charsetName)** | 使用指定方式进行解码 |

```java
//编码
String str = "ai你有";
byte[] byte1 = str.getBytes();
System.out.println(Arrays.toString(byte1));  //[97,105,-28,-67,-96,-27,-109,-97]
byte[] byte2 = str.getBytes("GBK");
System.out.println(Arrays.toString(byte2));  //[97,105,-60,-29,-45,-76]
```

```java
//解码
String str2 = new String(byte1);
System.out.println(str2);
String str3 = new String(byte1,"GBK");
System.out.println(str3); //乱码
```

#### 5.3.2 字符输入流

`java.io.Reader`抽象类是表示用于读取字符流的所有类的超类，可以读取字符信息到内存中

<font color=blue>**1. 基本方法** </font>

| 方法                  | 描述                                                  |
| --------------------- | ----------------------------------------------------- |
| close()               | 关闭此流并释放与此流相关联的任何系统资源              |
| int read()            | 从输入流读取一个字符                                  |
| int read(char[] cbuf) | 从输入流中读取一些字符，并将它们存储到字符数组 cbuf中 |

- **字符流**：底层就是字节流（<font color=red>**字符流 = 字节流 + 字符集**</font>）
- **特点**：
  - 输入流：一次读一个字节，遇到中文一次读多个字节(**根据字符集选择有关**)
  - 输出流：底层会把数据按照指定的编码方式进行编码，**变成字节写到文件中**

<font color=blue>**2. 使用场景：** </font>对于纯文本文件进行读写操作

<font color=blue>**3.FileReader** </font>

`java.io.FileReader`类是读取字符文件的便利类。构造时使用系统默认的字符编码和默认字节缓冲区。

> 小贴士：
>
> 1. 字符编码：字节与字符的对应规则。Windows系统的中文编码默认是**GBK编码表**。IDEA中UTF-8
>
> 2. 字节缓冲区：一个字节数组，用来临时存储字节数据

```java
//1. 创建字符输入流
// ①使用File对象创建流对象
File file = new File("a.txt");
FileReader fr = new FileReader(file);
// ②使用文件名称创建流对象
FileReader fr = new FileReader("b.txt");

//2.读取数据
//细节一：按字节进行读取，遇到文字，一次读取多个字节(GBK一次读两个，UTF-8一次读三个)，读取后解码，返回一个整数
//细节二：读到文件末尾，read方法返回
int ch;
while((ch=fr.read())!= -1){
    System.out.println((char)ch); 
}

/*空参read细节：
(1)read()默认也是一个字节一个字节的读取，如果遇到中文就会一次读取多个
(2)读取之后，方法的底层会进行解码并转成十进制，最终将这个十进制作为返回值，此十进制表示字符集上的数字
	英文：文件里面二进制数据 0110 0001
		read方法进行读取，解码并转成十进制97
	中文：文件里面二进制数据 1100110 10110001 10001001
    	read方法进行读取，解码并转成十进制27721
    	如果不想看见二进制数字，想要看见数字，需要将其进行强转*/

//3.释放资源
fr.close();
```

**使用字符数组读取**：`read(char[] cbuf)`，每次读取b的长度个字符到数组中，返回读取到的有效字符个数，读取到末尾时，返回`-1`

```java
FileReader fr = new FileReader("read.txt");
int len ；
// 定义字符数组，作为装字符数据的容器
char[] cbuf = new char[2];
// 循环读取
while ((len = fr.read(cbuf))!=-1) {
    System.out.println(new String(cbuf));
}
/*有参read(chars)细节：
	将读取数据、解码、强转三步进行合并，将强转之后的字符放置到数组中
	相当于：空参的read+强制类型转换*/
fr.close();
```

**获取有效的字符改进**，代码使用演示：

```java
FileReader fr = new FileReader("read.txt");
int len ；
char[] cbuf = new char[2];
while ((len = fr.read(cbuf))!=-1) {
    System.out.println(new String(cbuf,0,len)); //注意改进
}
fr.close();
```

#### 5.3.3 字符输出流

`java.io.Writer `抽象类是表示用于写出字符流的所有类的超类，将指定的字符信息写出到目的地

| 方法                                 | 描述                                                     |
| ------------------------------------ | -------------------------------------------------------- |
| write(int c)                         | 写入单个字符                                             |
| write(char[] cbuf)                   | 写入字符数组                                             |
| write(char[] cbuf, int off, int len) | 写入字符数组的某一部分,off数组的开始索引,len写的字符个数 |
| write(String str)                    | 写入字符串                                               |
| write(String str, int off, int len)  | 写入字符串的某一部分,off字符串的开始索引,len写的字符个数 |
| flush()                              | 刷新该流的缓冲                                           |
| close()                              | 关闭此流，但要先刷新它                                   |

`java.io.FileWriter `类是写出字符到文件的便利类。构造时使用系统默认的字符编码和默认字节缓冲区。

```java
//1.创建字符输出流对象
//细节一：参数时字符串表示的路径或File对象均可
//细节二：如果文件不存在会创建一个新的文件，但要保证父级路径存在
//细节三：如果文件已存在，则会清空文件，如果不想清空文件需要打开续写开关
//使用File对象创建流对象
File file = new File("a.txt");
FileWriter fw = new FileWriter(file);      
//使用文件名称创建流对象
FileWriter fw = new FileWriter("b.txt");

//2.写数据
//细节：如果write方法的参数是整数，但实际上写到本地文件中的整数在字符集上对应的字符
fw.write("你好威啊???"); //15个字节

//3.释放资源
fw.close();
```

<font color=blue>**1.字符流原理解析** </font>

- 创建字符输入流对象

  - 底层：关联文件，并创建**缓冲区**(长度为8192的字节数组)

- 读取数据

  - 底层：①判断缓冲区是否有数据可以读取

    ​	    ②缓冲区没有数据：就从文件中读取数据，装到缓冲区中，每次尽可能装满缓冲区

    ​					      如果文件中没有找到数据，返回-1

    ​	    ③缓冲区有数据：从缓冲区中读取

    ​	空参的read方法，一次读取一个字节，遇到中文一次读多个字节，把字节解码并转成十进制返回

    ​	有参的read方法，把读取字节、解码、强转三步合并，强转之后的字符放到数组中

<font color=blue>**2.关闭和刷新** </font>

因为内置缓冲区的原因，如果不关闭输出流，无法写出字符到文件中。但是关闭的流对象，是无法继续写出数据的。如果我们既想写出数据，又想继续使用流，就需要`flush` 方法了。

* `flush` ：将缓冲区中数据，刷新到本地文件中，刷新之后还可以继续往文件中写出数据
* `close `:先刷新缓冲区，然后通知系统释放资源。流对象不可以再被使用了

```java
FileWriter fw = new FileWriter("fw.txt");
// 写出数据，通过flush
fw.write('刷'); // 写出第1个字符
fw.flush();
fw.write('新'); // 继续写出第2个字符，写出成功
fw.flush();
      
// 写出数据，通过close
fw.write('关'); // 写出第1个字符
fw.close();
fw.write('闭'); // 继续写出第2个字符,【报错】java.io.IOException: Stream closed
fw.close();
```

> 小贴士：即便是flush方法写出了数据，操作的最后还是要调用close方法，释放系统资源

打断点，右键Debug，找到fw下缓冲区所在区域，可实时查看缓冲区情况

![image-20240706204445791](javaBasis_assets\缓冲区.png)

<font color=blue>**3.写出其他数据** </font>

- **写出字符数组** ：`write(char[] cbuf)` 和 `write(char[] cbuf, int off, int len)` ，每次可以写出字符数组中的数据，用法类似FileOutputStream，代码使用演示：

```java
public class FWWrite {
    public static void main(String[] args) throws IOException {
        FileWriter fw = new FileWriter("fw.txt");     
      	// 字符串转换为字节数组
      	char[] chars = "黑马程序员".toCharArray();
      	// 写出字符数组
      	fw.write(chars); // 黑马程序员
		// 写出从索引2开始，2个字节。索引2是'程'，两个字节，也就是'程序'。
        fw.write(b,2,2); // 程序
        fos.close();
    }
}
```

- **写出字符串**：`write(String str)` 和 `write(String str, int off, int len)` ，每次可以写出字符串中的数据，更为方便，代码使用演示：

```java
public class FWWrite {
    public static void main(String[] args) throws IOException {
        // 使用文件名称创建流对象
        FileWriter fw = new FileWriter("fw.txt");     
      	// 字符串
      	String msg = "黑马程序员";
      	// 写出字符数组
      	fw.write(msg); //黑马程序员
		// 写出从索引2开始，2个字节。索引2是'程'，两个字节，也就是'程序'。
        fw.write(msg,2,2);	// 程序
        fos.close();
    }
}
```

- **续写和换行**：操作类似于FileOutputStream。

```java
public class FWWrite {
    public static void main(String[] args) throws IOException {
        // 使用文件名称创建流对象，可以续写数据
        FileWriter fw = new FileWriter("fw.txt"，true);     
      	// 写出字符串
        fw.write("黑马");
      	// 写出换行
      	fw.write("\r\n");
      	// 写出字符串
  		fw.write("程序员");
      	// 关闭资源
        fw.close();
    }
}
输出结果:
黑马
程序员
```

> 小贴士：字符流，只能操作文本文件，不能操作图片，视频等非文本文件。
>
> 当我们单纯读或者写文本文件时  使用字符流 其他情况使用字节流

### 5.4 IO异常的处理

<font color=blue>**1.JDK7前处理** </font>

![image-20240706185558521](javaBasis_assets\字节异常.png)

之前一直把异常抛出，而实际开发中并不能这样处理，建议使用`try...catch...finally` 代码块处理异常部分

```java  
public class HandleException1 {
    public static void main(String[] args) {
      	// 声明变量
        FileWriter fw = null;
        try {
            //创建流对象
            fw = new FileWriter("fw.txt");
            // 写出数据
            fw.write("黑马程序员"); //黑马程序员
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (fw != null) {
                    fw.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```

<font color=blue>**2.JDK7的处理** </font>

JDK7优化后的`try-with-resource` 语句，该语句确保了每个资源在语句结束时关闭。所谓的资源（resource）是指在程序完成后，必须关闭的对象。

格式：

```java
try (创建流对象语句，如果多个,使用';'隔开) {
	// 读写数据
} catch (IOException e) {
	e.printStackTrace();
}
```

代码使用演示：

```java
public class HandleException2 {
    public static void main(String[] args) {
      	// 创建流对象
        try ( FileWriter fw = new FileWriter("fw.txt"); ) {
            // 写出数据
            fw.write("黑马程序员"); //黑马程序员
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

<font color=blue>**3.JDK9的改进** </font>

JDK9中`try-with-resource` 的改进，对于**引入对象**的方式，支持的更加简洁。被引入的对象，同样可以自动关闭，无需手动close，我们来了解一下格式。

改进前格式：

```java
// 被final修饰的对象
final Resource resource1 = new Resource("resource1");
// 普通对象
Resource resource2 = new Resource("resource2");
// 引入方式：创建新的变量保存
try (Resource r1 = resource1;
     Resource r2 = resource2) {
     // 使用对象
}
```

改进后格式：

```java
// 被final修饰的对象
final Resource resource1 = new Resource("resource1");
// 普通对象
Resource resource2 = new Resource("resource2");

// 引入方式：直接引入
try (resource1; resource2) {
     // 使用对象
}
```

改进后，代码使用演示：

```java
public class TryDemo {
    public static void main(String[] args) throws IOException {
       	// 创建流对象
        final  FileReader fr  = new FileReader("in.txt");
        FileWriter fw = new FileWriter("out.txt");
       	// 引入到try中
        try (fr; fw) {
          	// 定义变量
            int b;
          	// 读取数据
          	while ((b = fr.read())!=-1) {
            	// 写出数据
            	fw.write(b);
          	}
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

###### 综合练习

字节流和字符流的使用场景

- 字节流：**拷贝**任意类型的文件
- 字符流：
  - 读取**纯文本**文件中的数据
  - 往**纯文本**文件中写出数据

**练习1：拷贝文件夹**

要求：拷贝一个文件夹，需要考虑子文件夹

```java
public class Test01 {
    public static void main(String[] args) throws IOException {
        //1.创建对象表示 数据源
        File src = new File("D:\\aaa\\src");
        //2.创建对象表示 目的地
        File dest = new File("D:\\aaa\\dest");
        //3.调用方法开始拷贝
        copydir(src,dest);
    }

    //方法作用：拷贝文件夹(数据源，目的地)
    private static void copydir(File src, File dest) throws IOException {
        dest.mkdirs();
        //递归
        //1.进入数据源
        File[] files = src.listFiles();
        //2.遍历数组
        for (File file : files) {
            if(file.isFile()){ //是文件
                //3.判断文件，拷贝
                FileInputStream fis = new FileInputStream(file);
                FileOutputStream fos = new FileOutputStream(new File(dest,file.getName())); //将字节写到文件中，拷贝时以文件开始，到文件结束
                byte[] bytes = new byte[1024];
                int len;
                while((len = fis.read(bytes)) != -1){
                    fos.write(bytes,0,len);
                }
                fos.close();
                fis.close();
            }else {
                //4.判断文件夹，递归
                copydir(file, new File(dest,file.getName()));
            }
        }
    }
}
```

**练习2：文件加密**

 为了保证文件的安全性，就需要对原始文件进行加密存储，再使用的时候再对其进行解密处理。
	加密原理：对原始文件中的每一个字节数据进行更改，然后将更改以后的数据存储到新的文件中。
	解密原理：读取加密之后的文件，按照加密的规则反向操作，变成原始文件。

```java
扩展：异或^原理
    两边不同：true
    两边相同：false
两边若都为数字：0为false，1为true
    100：1100100
    10：1010
    对齐操作1100100
     	^     1010
    _______________
    	   1101110
    十进制：110
所以：100 ^ 10 = 110
     110 ^ 10 = 100
```

```java
public class Test02 {
    public static void main(String[] args) throws IOException {
    }

    public static void encryptionAndReduction(File src, File dest) throws IOException {
        //1.创建对象关联原始文件
        FileInputStream fis = new FileInputStream(src);
        //2.创建对象关联加密文件
        FileOutputStream fos = new FileOutputStream(dest);//若是解密操作，直接在此处更改文件
        //3.加密处理
        int b;
        while ((b = fis.read()) != -1) {
            fos.write(b ^ 2);
        }
        //4.释放资源
        fos.close();
        fis.close();
    }
}
```

**练习3：数字排序**

文本文件中有以下的数据：2-1-9-4-7-8
 将文件中的数据进行排序，变成以下的数据：1-2-4-7-8-9

实现方式一：

```java
public class Test03 {
    public static void main(String[] args) throws IOException {
        //1.读取数据
        FileReader fr = new FileReader("myio\\a.txt");
        StringBuilder sb = new StringBuilder(); //将读取到的数据进行拼接
        int ch;
        while((ch = fr.read()) != -1){
            sb.append((char)ch); //直接将数据拼接，不需要打印
        }
        fr.close();
        System.out.println(sb);
        
        //2.排序
        String str = sb.toString();
        String[] arrStr = str.split("-");//2-1-9-4-7-8
        ArrayList<Integer> list = new ArrayList<>();//定义集合
        for (String s : arrStr) {
            int i = Integer.parseInt(s); //遍历，进行类型转换String->Int
            list.add(i);
        }
        Collections.sort(list);
        System.out.println(list);
        
        //3.写出
        FileWriter fw = new FileWriter("myio\\a.txt");
        for (int i = 0; i < list.size(); i++) {
            if(i == list.size() - 1){
                fw.write(list.get(i) + "");
            }else{
                fw.write(list.get(i) + "-");
            }
        }
        fw.close();
    }
}
```

实现方式二：

```java
public class Test04 {
    public static void main(String[] args) throws IOException {
        /*细节1：文件中的数据不要换行
		  细节2:bom头，文件开头输出前有隐含的字符信息*/
        //1.读取数据
        FileReader fr = new FileReader("myio\\a.txt");
        StringBuilder sb = new StringBuilder();
        int ch;
        while((ch = fr.read()) != -1){
            sb.append((char)ch);
        }
        fr.close();
        System.out.println(sb);
        
        //2.排序
        Integer[] arr = Arrays.stream(sb.toString()
                                      .split("-"))
            .map(Integer::parseInt)
            .sorted()
            .toArray(Integer[]::new);
        
        //3.写出
        FileWriter fw = new FileWriter("myio\\a.txt");
        String s = Arrays.toString(arr).replace(", ","-");
        String result = s.substring(1, s.length() - 1);
        fw.write(result);
        fw.close();
    }
}
```

---



## 6 IO高级流

### 6.1 缓冲流

缓冲流，也叫高效流，是对4个基本的`FileXxx` 流的增强，所以也是4个流，按照数据类型分类：

* **字节缓冲流**：`BufferedInputStream`，`BufferedOutputStream` 
* **字符缓冲流**：`BufferedReader`，`BufferedWriter`

缓冲流的基本原理，是在创建流对象时，会创建一个内置的默认大小的缓冲区数组，通过缓冲区读写，**减少系统IO次数**，从而提高读写的效率

#### 6.1.1 字节缓冲流

<font color=blue>**1. 原理** </font>

底层自带了长度为8192的缓冲区提高性能

* `public BufferedInputStream(InputStream in)` ：把基本流**包装**为高级流，提高读取数据的性能
* `public BufferedOutputStream(OutputStream out)`： 把基本流**包装**成高级流，提高写出数据的性能

构造举例，代码如下：

```java
// 创建字节缓冲输入流
BufferedInputStream bis = new BufferedInputStream(new FileInputStream("bis.txt"));
// 创建字节缓冲输出流
BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("bos.txt"));

bos.close();
bis.close(); //如果调用缓冲流，则不需要再对输入输出流进行关闭
```

<font color=blue>**2. 效率测试** </font>

查询API，缓冲流读写方法与基本的流是一致的，通过复制大文件（375MB），测试它的效率

- 基本流：

```java
public class BufferedDemo {
    public static void main(String[] args) throws FileNotFoundException {
        // 记录开始时间
      	long start = System.currentTimeMillis();
		// 创建流对象
        try (
        	FileInputStream fis = new FileInputStream("jdk9.exe");
        	FileOutputStream fos = new FileOutputStream("copy.exe")
        ){
        	// 读写数据
            int b;
            while ((b = fis.read()) != -1) {
                fos.write(b);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
		// 记录结束时间
        long end = System.currentTimeMillis();
        System.out.println("普通流复制时间:"+(end - start)+" 毫秒");
    }
}
十几分钟过去了...
```

- 缓冲流：

```java
public class BufferedDemo {
    public static void main(String[] args) throws FileNotFoundException {
        // 记录开始时间
      	long start = System.currentTimeMillis();
		// 创建流对象
        try (
        	BufferedInputStream bis = new BufferedInputStream(new FileInputStream("jdk9.exe"));
	     BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("copy.exe"));
        ){
        // 读写数据
            int b;
            while ((b = bis.read()) != -1) {
                bos.write(b);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
		// 记录结束时间
        long end = System.currentTimeMillis();
        System.out.println("缓冲流复制时间:"+(end - start)+" 毫秒");
    }
}
缓冲流复制时间:8016 毫秒
```

<font color=blue>**3. 如何更快了？** </font>

使用数组的方式：

```java
public class BufferedDemo {
    public static void main(String[] args) throws FileNotFoundException {
      	// 记录开始时间
        long start = System.currentTimeMillis();
		// 创建流对象
        try (
			BufferedInputStream bis = new BufferedInputStream(new FileInputStream("jdk9.exe"));
		 BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("copy.exe"));
        ){
          	// 读写数据
            int len;
            byte[] bytes = new byte[8*1024];
            while ((len = bis.read(bytes)) != -1) {
                bos.write(bytes, 0 , len);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
		// 记录结束时间
        long end = System.currentTimeMillis();
        System.out.println("缓冲流使用数组复制时间:"+(end - start)+" 毫秒");
    }
}
缓冲流使用数组复制时间:666 毫秒
```

字节缓冲流提高效率的原理：虽然缓冲区也是一个字节一个字节的读，但是它都是放置在内存中进行倒手，内存的处理是非常快，<font color=red>**真正节约的是和硬盘间的操作时间**</font>。如果是数组，则变的是中间倒手的容器，一次定义多个数组，会更提高效率。

![image-20240706213335258](javaBasis_assets\缓冲流提高效率.png)

#### 6.1.2 字符缓冲流

原理：底层自带了长度为8192的缓冲区提高性能

* `public BufferedReader(Reader in)` ：创建一个新的缓冲输入流。 
* `public BufferedWriter(Writer out)`： 创建一个新的缓冲输出流。

```java
// 创建字符缓冲输入流
BufferedReader br = new BufferedReader(new FileReader("br.txt"));
// 创建字符缓冲输出流
BufferedWriter bw = new BufferedWriter(new FileWriter("bw.txt")); 
```

特有方法：

* BufferedReader：`public String readLine()`: 读一行数据，没有数据可读时返回null
* BufferedWriter：`public void newLine()`: 跨平台的换行(方法的底层会先判断操作系统，然后进行换行)

<font color=blue>**1. readLine：读一行数据** </font>

```java
public class BufferedReaderDemo {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader("in.txt"));
		// 定义字符串,保存读取的一行文字
        String line  = null;
        //细节：readLine方法在读取时会一次读一整行，遇到回车换行结束，但是它不会把回车换行读到内存中
      	// 循环读取,读取到最后返回null
        while ((line = br.readLine())!=null) {
            System.out.print(line);
        }
        br.close();
    }
}
```

<font color=blue>**2. newLine：跨平台的换行** </font>

  ```java
public class BufferedWriterDemo throws IOException {
    public static void main(String[] args) throws IOException  {
      	// 创建流对象
		BufferedWriter bw = new BufferedWriter(new FileWriter("out.txt"));
      	// 写出数据
        bw.write("黑马");
      	// 写出换行
        bw.newLine();
        bw.write("程序");
        bw.newLine();
        bw.write("员");
        bw.newLine();
		// 释放资源
        bw.close();
    }
}
输出效果:
黑马
程序
员
  ```

<font color=blue>**3. 缓冲区为什么能提高性能？** </font>

- 缓冲流自带长度为**8192的缓冲区**
- 可以显著提高字节流的读写性能
- 对于字符流提升不明显，对于字符缓冲流而言关键点是两个特有的方法

###### 综合练习

- **拷贝文件**：用四种方式拷贝文件，并统计各自用时

字节流的基本流：一次读写一个字节

字节流的基本流：一次读写一个字节数组

字节缓冲流：一次读写一个字节

字节缓冲流：一次读写一个字节数组

```java
public class Test{
    public static void main(String[] args) throws IOException{
        long start = System.currentTimeMills();
		method1();
		method2();
		method3();
		method4();
		long end = System.currentTimeMillis();
		System.out.println((end-start)/1000.0+"秒");
    }
}
//1.字节流的基本流：一次读写一个字节
public static void method1() throws IOException{
    FileInputStream fis = new FileInputStream("E:\\aaa\\CentOS.iso");
    FileOutputStream fos = new FileOutputStream("myio\\copy.iso");
    int b;
    while((b=fis.read())!=-1){
        fos.write(b);
    }
    fos.close();
    fis.close();
} 
//2.字节流的基本流：一次读写一个字节数组
public static void method2() throws IOException{
    FileInputStream fis = new FileInputStream("E:\\aaa\\CentOS.iso");
    FileOutputStream fos = new FileOutputStream("myio\\copy.iso");
    byte[] bytes = new byte[8192];
    int len;
    while((len = fis.read(bytes))!=-1){
        fos.write(bytes,0,len);
    }
    fos.close();
    fis.close();
}
//3.字节缓冲流：一次读写一个字节
public static void method3() throws IOException{
    BufferedInputStream bis = new BufferedInputStream(new FileInputStream("E:\\aaa\\CentOS.iso"));
    BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("myio\\copy.iso"));
    int b;
    while((b=bis.read())!=-1){
        bos.write(b);
    }
    bos.close();
    bis.close();
} 
//4.字节缓冲流：一次读写一个字节数组
```

- **文本排序**：将《出师表》的文章顺序进行恢复到一个新文件中

```
3.侍中、侍郎郭攸之、费祎、董允等，此皆良实，志虑忠纯，是以先帝简拔以遗陛下。愚以为宫中之事，事无大小，悉以咨之，然后施行，必得裨补阙漏，有所广益。
8.愿陛下托臣以讨贼兴复之效，不效，则治臣之罪，以告先帝之灵。若无兴德之言，则责攸之、祎、允等之慢，以彰其咎；陛下亦宜自谋，以咨诹善道，察纳雅言，深追先帝遗诏，臣不胜受恩感激。
4.将军向宠，性行淑均，晓畅军事，试用之于昔日，先帝称之曰能，是以众议举宠为督。愚以为营中之事，悉以咨之，必能使行阵和睦，优劣得所。
2.宫中府中，俱为一体，陟罚臧否，不宜异同。若有作奸犯科及为忠善者，宜付有司论其刑赏，以昭陛下平明之理，不宜偏私，使内外异法也。
1.先帝创业未半而中道崩殂，今天下三分，益州疲弊，此诚危急存亡之秋也。然侍卫之臣不懈于内，忠志之士忘身于外者，盖追先帝之殊遇，欲报之于陛下也。诚宜开张圣听，以光先帝遗德，恢弘志士之气，不宜妄自菲薄，引喻失义，以塞忠谏之路也。
9.今当远离，临表涕零，不知所言。
6.臣本布衣，躬耕于南阳，苟全性命于乱世，不求闻达于诸侯。先帝不以臣卑鄙，猥自枉屈，三顾臣于草庐之中，咨臣以当世之事，由是感激，遂许先帝以驱驰。后值倾覆，受任于败军之际，奉命于危难之间，尔来二十有一年矣。
7.先帝知臣谨慎，故临崩寄臣以大事也。受命以来，夙夜忧叹，恐付托不效，以伤先帝之明，故五月渡泸，深入不毛。今南方已定，兵甲已足，当奖率三军，北定中原，庶竭驽钝，攘除奸凶，兴复汉室，还于旧都。此臣所以报先帝而忠陛下之职分也。至于斟酌损益，进尽忠言，则攸之、祎、允之任也。
5.亲贤臣，远小人，此先汉所以兴隆也；亲小人，远贤臣，此后汉所以倾颓也。先帝在时，每与臣论此事，未尝不叹息痛恨于桓、灵也。侍中、尚书、长史、参军，此悉贞良死节之臣，愿陛下亲之信之，则汉室之隆，可计日而待也。
```

**案例分析**

1. 逐行读取文本信息。
2. 把读取到的文本存储到集合中
3. 对集合中的文本进行排序
4. 遍历集合，按顺序，写出文本信息。

**案例实现**

```java
public class Demo05Test {
    public static void main(String[] args) throws IOException {
        //1.创建ArrayList集合,泛型使用String
        ArrayList<String> list = new ArrayList<>();
        //2.创建BufferedReader对象,构造方法中传递FileReader对象
        BufferedReader br = new BufferedReader(new FileReader("10_IO\\in.txt"));
        //3.创建BufferedWriter对象,构造方法中传递FileWriter对象
        BufferedWriter bw = new BufferedWriter(new FileWriter("10_IO\\out.txt"));
        //4.使用BufferedReader对象中的方法readLine,以行的方式读取文本
        String line;
        while((line = br.readLine())!=null){
            //5.把读取到的文本存储到ArrayList集合中
            list.add(line);
        }
        //6.使用Collections集合工具类中的方法sort,对集合中的元素按照自定义规则排序
        Collections.sort(list, new Comparator<String>() {
            /*o1-o2:升序；o2-o1:降序*/
            @Override
            public int compare(String o1, String o2) {
                //依次比较集合中两个元素的首字母,升序排序
                return o1.charAt(0)-o2.charAt(0);
            }
        });
        //7.遍历ArrayList集合,获取每一个元素
        for (String s : list) {
            //8.使用BufferedWriter对象中的方法wirte,把遍历得到的元素写入到文本中(内存缓冲区中)
            bw.write(s);
            //9.写换行
            bw.newLine();
        }
        //10.释放资源
        bw.close();
        br.close();
    }
}
```

- **软件运行次数**：实现一个验证程序运行次数的小程序，要求如下：

  - 当程序运行超过三次时给出提示：本软件只能免费使用3次，欢迎您注册会员后继续使用

  - 程序运行演示如下：
    - 第一次运行控制台输出：欢迎使用本软件，第一次使用免费~
    - 第二次运行控制台输出：欢迎使用本软件，第二次使用免费~
    - 第三次运行控制台输出：欢迎使用本软件，第三次使用免费~
    - 第四次及之后运行控制台输出：本软件只能免费使用三次，欢迎您注册会员后继续使用~

```java
public class Test{
    public static void main(String[] args) throws IOException{
        //1.把文件中的数字读取到内存中
        //原则：IO流随用随创建。什么时候不用什么时候关闭
        BufferedReader br = new BufferedReader(new FileReader("myio\\count.txt"));
        String line = br.readLine();
        int count = Integer.parseInt(line);
        //表示当前软件又运行了一次
        count++;
        //2.判断：<=3正常运行,>3不能运行
        if(count<=3){
            System.out.println("欢迎使用本软件，第"+count+"次使用免费~")
        }else{
           System.out.println("本软件只能免费使用三次，欢迎您注册会员后继续使用~") 
        } 
        //3.将当前自增之后的count写出到文件中，不然次数不会更新
        BufferedWriter bw = new BufferedWriter(new FileWriter("myio\\count.txt"));
        bw.write(count+""); //变为字符串，才可以原样写出
    }
}
```



### 6.2 转换流

![image-20240707150320115](javaBasis_assets\转换流.png)

#### 6.2.1 InputStreamReader类

转换流`java.io.InputStreamReader`，是Reader的子类，是从<font color=red>**字节流到字符流的桥梁**</font>。它读取字节，并使用指定的字符集将其解码为字符。它的字符集可以由名称指定，也可以接受平台的默认字符集。 

* `InputStreamReader(InputStream in)`: 创建一个使用默认字符集的字符流。 
* `InputStreamReader(InputStream in, String charsetName)`: 创建一个指定字符集的字符流。

构造举例，代码如下： 

```java
InputStreamReader isr = new InputStreamReader(new FileInputStream("in.txt"));
InputStreamReader isr2 = new InputStreamReader(new FileInputStream("in.txt") , "GBK");
```

**指定编码读取**

```java
public class ReaderDemo2 {
    public static void main(String[] args) throws IOException {
        //此类方案在JDK11后已被淘汰，需要掌握替代方案
        
      	// 定义文件路径,文件为gbk编码
        String FileName = "E:\\file_gbk.txt";
      	// 创建流对象,默认UTF8编码
        InputStreamReader isr = new InputStreamReader(new FileInputStream(FileName));
      	// 创建流对象,指定GBK编码
        InputStreamReader isr2 = new InputStreamReader(new FileInputStream(FileName) , "GBK");
		// 定义变量,保存字符
        int read;
      	// 使用默认编码字符流读取,乱码
        while ((read = isr.read()) != -1) {
            System.out.print((char)read); // ��Һ�
        }
        isr.close();
      
      	// 使用指定编码字符流读取,正常解析
        while ((read = isr2.read()) != -1) {
            System.out.print((char)read);// 大家好
        }
        isr2.close();
    }
}
```

```java
/*替代方案，需要掌握*/
FileReader fr = new FileReader("myio\\gbkfile.txt",Charset.forName("GBK"));
int ch;
while((ch=fr.read())!=-1){
    System.out.println((char)ch);
}
fr.close();
```

#### 6.2.2 OutputStreamWriter类

转换流`java.io.OutputStreamWriter` ，是Writer的子类，是**从字符流到字节流的桥梁**。使用指定的字符集将字符编码为字节。它的字符集可以由名称指定，也可以接受平台的默认字符集。 

- `OutputStreamWriter(OutputStream in)`: 创建一个使用默认字符集的字符流。 
- `OutputStreamWriter(OutputStream in, String charsetName)`: 创建一个指定字符集的字符流。

构造举例，代码如下： 

```java
OutputStreamWriter isr = new OutputStreamWriter(new FileOutputStream("out.txt"));
OutputStreamWriter isr2 = new OutputStreamWriter(new FileOutputStream("out.txt") , "GBK");
```

**指定编码写出**

```java
public class OutputDemo {
    public static void main(String[] args) throws IOException {
      	// 定义文件路径
        String FileName = "E:\\out.txt";
      	// 创建流对象,默认UTF8编码
        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream(FileName));
        // 写出数据
      	osw.write("你好"); // 保存为6个字节
        osw.close();
      	
		// 定义文件路径
		String FileName2 = "E:\\out2.txt";
     	// 创建流对象,指定GBK编码
        OutputStreamWriter osw2 = new OutputStreamWriter(new FileOutputStream(FileName2),"GBK");
        // 写出数据
      	osw2.write("你好");// 保存为4个字节
        osw2.close();
    }
}
```

```java
//替代方案
FileWriter fw = new FileWriter("myio\\c.txt",Charset.forName("GBK"));
fw.write("你好你好");
fw.close();
```

若出现乱码，文件另存为在编码处查看

![image-20240707152231470](javaBasis_assets\乱码解决.png)

**转换流理解图解**

<font color=red>**转换流是字节与字符间的桥梁！**</font>![](javaBasis_assets\2_zhuanhuan.jpg)

<font color=blue>**1. 转换文件编码**</font>

将GBK编码的文本文件，转换为UTF-8编码的文本文件。

①指定GBK编码的转换流，读取文本文件

②使用UTF-8编码的转换流，写出文本文件

- JDK11以前方案

  ```java
  InputStreamReader isr = new InputStreamReader(new FileInputStream("myio\\b.txt"),"GBK");
  OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream("myio\\d.txt"),"UTF-8");
  
  int b;
  while((b=isr.read())!=-1){
      osw.write(b);
  }
  osw.close();
  isr.close();
  ```

- 替代方案

  ```java
  FileReader fr = new FileReader("myio\\b.txt",Charset.forName("GBK"));
  FileWriter fw = new FileWriter("myio\\e.txt",Charset.forName("UTF-8"));
  
  int b;
  while((b=fr.read())!=-1){
      fw.write(b);
  }
  fw.close();
  fr.close();
  ```

<font color=blue>**2. 利用字节流读取文件中的数据**</font>

每次读取一整行，并且不能出现乱码

- 字节流在读取中文时会出现乱码，但是字符流可以搞定

- 字节流是没有读取一整行的方法的，只有字符缓冲流可以搞定

  ```java
  /*FileInputStream fis = new FileInputStream("myio\\a.txt");
  InputStreamReader isr = new InputStreamReader(fis);
  BufferedReader br = new BufferedReader(isr);
  String str = br.readLine();
  System.out.println(str);
  br.close();*/
  
  BufferedReader br = new BufferedReader(new InputStreamReader(new FileInputStream("myio\\a.txt")));
  String line;
  while((line = br.readLine())!=null){
      System.out.println(line);
  }
  br.close();
  ```



### 6.3 序列化

**序列化流/对象操作输出流**：属于字节流，可以把Java中的对象写到本地文件中

Java 提供了一种对象**序列化**的机制。用一个字节序列可以表示一个对象，该字节序列包含该`对象的数据`、`对象的类型`和`对象中存储的属性`等信息。字节序列写出到文件之后，相当于文件中**持久保存**了一个对象的信息。 

反之，该字节序列还可以从文件中读取回来，重构对象，对它进行**反序列化**。`对象的数据`、`对象的类型`和`对象中存储的数据`信息，都可以用来在内存中创建对象。看图理解序列化： ![](javaBasis_assets\3_xuliehua.jpg)

#### 6.3.1 ObjectOutputStream类

`java.io.ObjectOutputStream ` 类，将Java对象的原始数据类型写出到文件,实现对象的持久存储

| 构造方法                                    | 说明                       |
| ------------------------------------------- | -------------------------- |
| public ObjectOutputStream(OutputStream out) | 把基本流包装成高级流       |
| **成员方法**                                | **说明**                   |
| public final void writeObject(Object obj)   | 把对象序列化(写出)到文件中 |

序列化流的小细节：使用对象输出流将对象保存到文件时会出现NotSerializableException异常，需要让Javabean类实现Serializable接口

- 一个对象要想序列化，必须满足两个条件:

  * 该类必须实现`java.io.Serializable ` 接口，`Serializable` 是一个标记接口，不实现此接口的类将不会使任何状态序列化或反序列化，会抛出`NotSerializableException` 

    ```java
    //1.创建对象
    Student stu = new Student("zxy",23);
    //2.创建序列化流的对象/对象操作输出流
    ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("myio\\a.txt"));
    //3.写出数据
    oos.writeObject(stu);
    //4.释放数据
    oos.close();
    ```

  * 该类的所有属性必须是可序列化的。如果有一个属性不需要可序列化的，则该属性必须注明是瞬态的，使用`transient` 关键字修饰。


```java
public class Employee implements java.io.Serializable {
    public String name;
    public String address;
    public transient int age; // transient瞬态修饰成员,不会被序列化
    public void addressCheck() {
        System.out.println("Address  check : " + name + " -- " + address);
    }
}
```

2.写出对象方法

* `public final void writeObject (Object obj)` : 将指定的对象写出。

```java
public class SerializeDemo{
   	public static void main(String [] args)   {
    	Employee e = new Employee();
    	e.name = "zhangsan";
    	e.address = "beiqinglu";
    	e.age = 20; 
    	try {
      		// 创建序列化流对象
          ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("employee.txt"));
        	// 写出对象
        	out.writeObject(e);
        	// 释放资源
        	out.close();
        	fileOut.close();
        	System.out.println("Serialized data is saved"); // 姓名，地址被序列化，年龄没有被序列化。
        } catch(IOException i)   {
            i.printStackTrace();
        }
   	}
}
输出结果：
Serialized data is saved
```

#### 6.3.2 ObjectInputStream类

ObjectInputStream反序列化流，将之前使用ObjectOutputStream序列化的原始数据恢复为对象。 

| 构造方法                                  | 说明                                     |
| ----------------------------------------- | ---------------------------------------- |
| public ObjectInputStream(InputStream out) | 把基本流变成高级流                       |
| **成员方法**                              | **说明**                                 |
| public Object readObject()                | 把序列化到本地文件中的对象，读取到程序中 |

```java
public class DeserializeDemo {
   public static void main(String [] args)   {
        Employee e = null;
        try {		
             // 创建反序列化流
             FileInputStream fileIn = new FileInputStream("employee.txt");
             ObjectInputStream in = new ObjectInputStream(fileIn);
             // 读取一个对象
             e = (Employee) in.readObject();
             // 释放资源
             in.close();
             fileIn.close();
        }catch(IOException i) {
             // 捕获其他异常
             i.printStackTrace();
             return;
        }catch(ClassNotFoundException c)  {
        	// 捕获类找不到异常
             System.out.println("Employee class not found");
             c.printStackTrace();
             return;
        }
        // 无异常,直接打印输出
        System.out.println("Name: " + e.name);	// zhangsan
        System.out.println("Address: " + e.address); // beiqinglu
        System.out.println("age: " + e.age); // 0
    }
}
```

**对于JVM可以反序列化对象，它必须是能够找到class文件的类。如果找不到该类的class文件，则抛出一个 `ClassNotFoundException` 异常。**  

**版本号问题**

**另外，当JVM反序列化对象时，能找到class文件，但是class文件在序列化对象之后发生了修改，那么反序列化操作也会失败，抛出一个`InvalidClassException`异常。**发生这个异常的原因如下：

* 该类的序列版本号与从流中读取的类描述符的版本号不匹配 
* 该类包含未知数据类型 
* 该类没有可访问的无参数构造方法 

`Serializable` 接口给需要序列化的类，提供了一个序列版本号。`serialVersionUID` 该版本号的目的在于验证序列化的对象和对应类是否版本匹配。

```java
public class Employee implements java.io.Serializable {
     // 加入序列版本号
     private static final long serialVersionUID = 1L;
     public String name;
     public String address;
     // 添加新的属性 ,重新编译, 可以反序列化,该属性赋为默认值.
     public int eid; 

     public void addressCheck() {
         System.out.println("Address  check : " + name + " -- " + address);
     }
}
```

- 如果想要自动生成版本号

  - 复制Serializable，打开Settings

    ![image-20240707163027534](javaBasis_assets\设置.png)

  - 选中类别，直接生成版本号

    <img src="C:/Users/周歆怡/Desktop/周记/JavaBasis/assets/版本.png" alt="image-20240707163119000" style="zoom:67%;" />

**序列化流**/**反序列化流的细节汇总**：

① 使用序列化流将对象写到文件时，需要让Javabean类实现Serializable接口，否则会出现NotSerializableException异常

② 序列化流写到文件中的数据是不能修改的，一旦修改就无法再次读回来了 

③ 序列化对象后，修改了Javabean类，再次反序列化，会不会有问题？

​	会出问题，会抛出InvalidClassException异常

​	解决方案：给Javabean类添加serialVersionUID(序列号、版本号)

④ 如果一个对象中的某个成员变量的值不想被序列化，该如何实现？

​	解决方案：给该成员变量加transient关键字修饰，该关键字标记的成员变量不参与序列化过程

#### 6.3.3 序列化集合

1. 将存有多个自定义对象的集合序列化操作，保存到`list.txt`文件中。
2. 反序列化`list.txt` ，并遍历集合，打印对象信息。

**案例分析**

1. 把若干学生对象 ，保存到集合中。
2. 把集合序列化。
3. 反序列化读取时，只需要读取一次，转换为集合类型。
4. 遍历集合，可以打印所有的学生信息

**案例实现**

```java
public class SerTest {
	public static void main(String[] args) throws Exception {
		// 创建 学生对象
		Student student = new Student("老王", "laow");
		Student student2 = new Student("老张", "laoz");
		Student student3 = new Student("老李", "laol");

		ArrayList<Student> arrayList = new ArrayList<>();
		arrayList.add(student);
		arrayList.add(student2);
		arrayList.add(student3);
		// 序列化操作
		// serializ(arrayList);
		
		// 反序列化  
		ObjectInputStream ois  = new ObjectInputStream(new FileInputStream("list.txt"));
		// 读取对象,强转为ArrayList类型
		ArrayList<Student> list  = (ArrayList<Student>)ois.readObject();
		
      	for (int i = 0; i < list.size(); i++ ){
          	Student s = list.get(i);
        	System.out.println(s.getName()+"--"+ s.getPwd());
      	}
	}

	private static void serializ(ArrayList<Student> arrayList) throws Exception {
		// 创建 序列化流 
		ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("list.txt"));
		// 写出对象
		oos.writeObject(arrayList);
		// 释放资源
		oos.close();
	}
}
```


###  6.4 打印流

平时我们在控制台打印输出，是调用`print`方法和`println`方法完成的，这两个方法都来自于`java.io.PrintStream`类，该类能够方便地打印各种数据类型的值，是一种便捷的输出方式

![image-20240707184915272](javaBasis_assets\打印流.png)

- 分类：打印流一般指：PrintStream,PrintWriter两个类

- 特点：

  - 特点1：打印流只操作文件目的地，不操作数据源

  - 特点2：特有的写出方法，可以实现数据原样写出

  - 特点3：特有的写出方法，可以实现自动刷新，自动换行

    ​		**打印一次数据 = 写出 + 换行 + 刷新**

- 字节打印流

字节流底层没有缓冲区，开不开自动刷新都一样

| 构造方法                                                     | 说明                     |
| ------------------------------------------------------------ | ------------------------ |
| public PrintStream(OutputStream/File/String)                 | 关联字节输出流/文件/路径 |
| public PrintStream(String fileName,Charset charset)          | 指定字符编码             |
| public PrintStream(OutputStream out,boolean autoFlush)       | 自动刷新                 |
| public PrintStream(OutputStream out,boolean autoFlush,String encoding) | 指定字符编码且自动刷新   |

| 成员方法                                          | 说明                                       |
| ------------------------------------------------- | ------------------------------------------ |
| public void write(int b)                          | 常规方法：规则跟之前一样，将指定的字节写出 |
| public void println()                             | 特有方法：打印任意数据，自动刷新，自动换行 |
| public void print                                 | 特有方法：打印任意数据，不换行             |
| public void printf(String format,Object ... args) | 特有方法：带有占位符的打印语句，不换行     |

`System.out`就是`PrintStream`类型的，只不过它的流向是系统规定的，打印在控制台上。不过，既然是流对象，我们就可以玩一个"小把戏"，改变它的流向。

```java
public class PrintDemo {
    public static void main(String[] args) throws IOException {
		// 调用系统的打印流,控制台直接输出97
        System.out.println(97);
		// 创建打印流,指定文件的名称
        PrintStream ps = new PrintStream("ps.txt");
      	// 设置系统的打印流流向,输出到ps.txt
        System.setOut(ps);
      	// 调用系统的打印流,ps.txt中输出97
        System.out.println(97);
    }
}
```

### 6.5 压缩流和解压缩流

压缩流：负责压缩文件或者文件夹

解压缩流：负责把压缩包中的文件和文件夹解压出来

​	解压本质：把每一个ZipEntry按照层级拷贝到本地另一个文件夹中

![image-20240707191510666](javaBasis_assets\压缩流.png)

```java
/*解压缩流*/
public class ZipStreamDemo1 {
    public static void main(String[] args) throws IOException {
        //1.创建一个File表示要解压的压缩包
        File src = new File("D:\\aaa.zip");
        //2.创建一个File表示解压的目的地
        File dest = new File("D:\\");
        //调用方法
        unzip(src,dest);
    }

    //定义一个方法用来解压
    public static void unzip(File src,File dest) throws IOException {
        //解压的本质：把压缩包里面的每一个文件或者文件夹读取出来，按照层级拷贝到目的地当中
        //创建一个解压缩流用来读取压缩包中的数据
        ZipInputStream zip = new ZipInputStream(new FileInputStream(src));
        //要先获取到压缩包里面的每一个zipentry对象
        //表示当前在压缩包中获取到的文件或者文件夹
        ZipEntry entry;
        while((entry = zip.getNextEntry()) != null){
            System.out.println(entry);
            if(entry.isDirectory()){
                //文件夹：需要在目的地dest处创建一个同样的文件夹
                File file = new File(dest,entry.toString());
                file.mkdirs();
            }else{
               //文件：需要读取到压缩包中的文件，并把他存放到目的地dest文件夹中（按照层级目录进行存放）
                FileOutputStream fos = new FileOutputStream(new File(dest,entry.toString()));
                int b;
                while((b = zip.read()) != -1){
                    //写到目的地
                    fos.write(b);
                }
                fos.close();
                //表示在压缩包中的一个文件处理完毕了。
                zip.closeEntry();
            }
        }
        zip.close();
    }
}
```

```java
public class ZipStreamDemo2 {
    public static void main(String[] args) throws IOException {
        /*压缩流
         *需求：把D:\\a.txt打包成一个压缩包* */
        //1.创建File对象表示要压缩的文件
        File src = new File("D:\\a.txt");
        //2.创建File对象表示压缩包的位置
        File dest = new File("D:\\");
        //3.调用方法用来压缩
        toZip(src,dest);
    }

    /*作用：压缩
    * 参数一：表示要压缩的文件
    * 参数二：表示压缩包的位置* */
    public static void toZip(File src,File dest) throws IOException {
        //1.创建压缩流关联压缩包
        ZipOutputStream zos = new ZipOutputStream(new FileOutputStream(new File(dest,"a.zip")));
        //2.创建ZipEntry对象，表示压缩包里面的每一个文件和文件夹
        //参数：压缩包里面的路径
        ZipEntry entry = new ZipEntry("aaa\\bbb\\a.txt");
        //3.把ZipEntry对象放到压缩包当中
        zos.putNextEntry(entry);
        //4.把src文件中的数据写到压缩包当中
        FileInputStream fis = new FileInputStream(src);
        int b;
        while((b = fis.read()) != -1){
            zos.write(b);
        }
        zos.closeEntry();
        zos.close();
    }
}
```

```java
public class ZipStreamDemo3 {
    public static void main(String[] args) throws IOException {
        /*压缩流
        需求：把D:\\aaa文件夹压缩成一个压缩包
         * */
        //1.创建File对象表示要压缩的文件夹
        File src = new File("D:\\aaa");
        //2.创建File对象表示压缩包放在哪里（压缩包的父级路径）
        File destParent = src.getParentFile();//D:\\
        //3.创建File对象表示压缩包的路径
        File dest = new File(destParent,src.getName() + ".zip");
        //4.创建压缩流关联压缩包
        ZipOutputStream zos = new ZipOutputStream(new FileOutputStream(dest));
        //5.获取src里面的每一个文件，变成ZipEntry对象，放入到压缩包当中
        toZip(src,zos,src.getName());//aaa
        //6.释放资源
        zos.close();
    }

    /*作用：获取src里面的每一个文件，变成ZipEntry对象，放入到压缩包当中
    *   参数一：数据源
    *   参数二：压缩流
    *   参数三：压缩包内部的路径
    * */
    public static void toZip(File src,ZipOutputStream zos,String name) throws IOException {
        //1.进入src文件夹
        File[] files = src.listFiles();
        //2.遍历数组
        for (File file : files) {
            if(file.isFile()){
                //3.判断-文件，变成ZipEntry对象，放入到压缩包当中
                ZipEntry entry = new ZipEntry(name + "\\" + file.getName());//aaa\\no1\\a.txt
                zos.putNextEntry(entry);
                //读取文件中的数据，写到压缩包
                FileInputStream fis = new FileInputStream(file);
                int b;
                while((b = fis.read()) != -1){
                    zos.write(b);
                }
                fis.close();
                zos.closeEntry();
            }else{
                //4.判断-文件夹，递归
                toZip(file,zos,name + "\\" + file.getName());
                //     no1            aaa   \\   no1
            }
        }
    }
}
```

### 6.6 工具包（Commons-io）

介绍：Commons是apache开源基金组织提供的工具包，里面有很多帮助我们提高开发效率的API

比如：

​	StringUtils   字符串工具类

​	NumberUtils   数字工具类 

​	ArrayUtils   数组工具类  

​	RandomUtils   随机数工具类

​	DateUtils   日期工具类 

​	StopWatch   秒表工具类 

​	ClassUtils   反射工具类  

​	SystemUtils   系统工具类  

​	MapUtils   集合工具类

​	Beanutils   bean工具类

​	Commons-io io的工具类

​	等等.....

其中：Commons-io是apache开源基金组织提供的一组有关IO操作的开源工具包。

作用：提高IO流的开发效率。

使用方式：

1，新建lib文件夹

2，把第三方jar包粘贴到文件夹中

3，右键点击add as a library

代码示例：

```java
public class CommonsIODemo1 {
    public static void main(String[] args) throws IOException {
        /*FileUtils类
static void copyFile(File srcFile, File destFile)                  复制文件
static void copyDirectory(File srcDir, File destDir)               复制文件夹
static void copyDirectoryToDirectory(File srcDir, File destDir)    复制文件夹
static void deleteDirectory(File directory)                        删除文件夹
static void cleanDirectory(File directory)                         清空文件夹
static String readFileToString(File file, Charset encoding)        读取文件中的数据变成字符串
static void write(File file, CharSequence data, String encoding)   写出数据

           IOUtils类
public static int copy(InputStream input, OutputStream output)      复制文件
public static int copyLarge(Reader input, Writer output)            复制大文件
public static String readLines(Reader input)                        读取数据
public static void write(String data, OutputStream output)          写出数据*/

        /* File src = new File("myio\\a.txt");
        File dest = new File("myio\\copy.txt");
        FileUtils.copyFile(src,dest);*/

        /*File src = new File("D:\\aaa");
        File dest = new File("D:\\bbb");
        FileUtils.copyDirectoryToDirectory(src,dest);*/

        /*File src = new File("D:\\bbb");
        FileUtils.cleanDirectory(src);*/
    }
}
```

### 6.7 工具包（hutool）

介绍：Commons是国人开发的开源工具包，里面有很多帮助我们提高开发效率的API

比如：

​	DateUtil  日期时间工具类 

​	TimeInterval  计时器工具类 

​	StrUtil  字符串工具类

​	HexUtil   16进制工具类

​	HashUtil   Hash算法类

​	ObjectUtil  对象工具类

​	ReflectUtil   反射工具类

​	TypeUtil  泛型类型工具类

​	PageUtil  分页工具类

​	NumberUtil  数字工具类

使用方式：

1，新建lib文件夹

2，把第三方jar包粘贴到文件夹中

3，右键点击add as a library

代码示例：

```java
public class Test1 {
    public static void main(String[] args) {
    /*
        FileUtil类:
                file：根据参数创建一个file对象
                touch：根据参数创建文件

                writeLines：把集合中的数据写出到文件中，覆盖模式。
                appendLines：把集合中的数据写出到文件中，续写模式。
                readLines：指定字符编码，把文件中的数据，读到集合中。
                readUtf8Lines：按照UTF-8的形式，把文件中的数据，读到集合中

                copy：拷贝文件或者文件夹
    */


       /* File file1 = FileUtil.file("D:\\", "aaa", "bbb", "a.txt");
        System.out.println(file1);//D:\aaa\bbb\a.txt

        File touch = FileUtil.touch(file1);
        System.out.println(touch);

        ArrayList<String> list = new ArrayList<>();
        list.add("aaa");
        list.add("aaa");
        list.add("aaa");

        File file2 = FileUtil.writeLines(list, "D:\\a.txt", "UTF-8");
        System.out.println(file2);*/

      /*  ArrayList<String> list = new ArrayList<>();
        list.add("aaa");
        list.add("aaa");
        list.add("aaa");
        File file3 = FileUtil.appendLines(list, "D:\\a.txt", "UTF-8");
        System.out.println(file3);*/
        List<String> list = FileUtil.readLines("D:\\a.txt", "UTF-8");
        System.out.println(list);
    }
}
```

---



# 网络编程



## 1 多线程

### 1.1 多线程基本概念 

<font color=blue>**1. 什么是进程和线程？**</font>

**进程**：<font color=red>**正在运行的程序**</font>

- **独立性**：能独立运行的基本单位，系统分配资源和调度的独立单位
- **动态性**：进程实质是程序的一次执行过程，动态产生，动态消亡
- **并发性**：任何进程都可同其他进程一起并发执行

**线程**：<font color=red>**应用软件中相互独立、同时运行的功能**</font>

- <font color=red>**线程是操作系统能够运行调度的最小单位**</font>。被包含在进程之中，是**进程中实际运作单位**。
- 是进程中的单个顺序控制流，是**一条执行路径**
  - 单线程：一个进程如果只有一条执行路径，则称为单线程程序
  - 多线程：一个进程如果有多条执行路径，则称为多线程程序

​	<img src="javaBasis_assets\04_多线程示例.png" style="zoom:67%;" />

<font color=blue>**2. 什么是多线程技术？**</font>

- 从软件或者硬件上实现多个线程并发执行的技术。
- 具有多线程能力的计算机因有硬件支持而能够在同一时间执行多个线程，提升性能。
- **应用场景**：
  - 软件中的耗时操作：拷贝、迁移大文件；加载大量资源文件
  - 所有的聊天软件
  - 所有的后台服务器
- **多线程的作用**：**提高效率**

<font color=blue>**3. 什么是并发和并行？**</font>

+ **并行**：在同一时刻，有多个指令在<font color=red>**多个CPU**</font>上**同时**执行。

  <img src="javaBasis_assets\02_并行.png" alt="02_并行" style="zoom:50%;" />

+ **并发**：在同一时刻，有多个指令在<font color=red>**单个CPU**</font>上**交替**执行。

  <img src="javaBasis_assets\03_并发.png" alt="03_并发" style="zoom:50%;" />

> 例如：2核4线程 - 可同时运行4个线程(在计算机中任意4条线程随机切换)并发并行在计算机中可同时发生

<font color=blue>**4. 线程的生命周期**</font>

![image-20240819164249852](javaBasis_assets\image-20240819164249852.png)

==面试题：sleep方法会让线程睡眠，但睡眠时间到之后，会立马执行下面代码吗？==

不会，是变为就绪状态，会继续抢CPU，抢到了才会进行后续代码

<font color=blue>**5. 多线程的六种状态**</font>

![image-20240822104935972](javaBasis_assets\image-20240822104935972.png)

| 线程状态 | 表示          | 描述             |
| -------- | ------------- | ---------------- |
| 新建状态 | NEW           | 创建线程对象     |
| 就绪状态 | RUNNABLE      | start方法        |
| 阻塞状态 | BLOCKED       | 无法获得锁对象   |
| 等待状态 | WAITING       | wait方法         |
| 计时等待 | TIMED_WAITING | sleep方法        |
| 结束状态 | TERMINATED    | 全部代码运行完毕 |



### 1.2 多线程实现方式

<font color=blue>**1. 继承Thread类**</font>

- **方法介绍**

  | 方法名       | 说明                                        |
  | ------------ | ------------------------------------------- |
  | void run()   | 在线程开启后，此方法将被调用执行            |
  | void start() | 使此线程开始执行，Java虚拟机会调用run方法() |

- **实现步骤**

  - 定义一个类MyThread<font color=red>**继承Thread类**</font>
  - 在MyThread类中<font color=red>**重写run()方法**</font>
  - 创建MyThread类的<font color=red>**对象**</font>，并<font color=red>**启动线程**</font>

- **代码演示**

  ```java
  public class MyThread extends Thread {
      @Override
      public void run() {
          //书写线程要执行的代码，例如打印循环
          for(int i=0; i<100; i++) {
              System.out.println(getName()+i);
          }
      }
  }
  public class MyThreadDemo {
      public static void main(String[] args) {
          MyThread my1 = new MyThread();
          MyThread my2 = new MyThread();
          
          my1.setName("线程1");
          my2.setName("线程2");
  
  //        my1.run();用start方法不用run方法
  //        my2.run();
  
          //void start() 导致此线程开始执行; Java虚拟机调用此线程的run方法
          my1.start();
          my2.start();
      }
  }
  ```

  ==**注意**==：

  - ==为什么要重写run()方法？==

    因为run()是用来封装被线程执行的代码

  - ==run()方法和start()方法的区别？==

    run()：封装线程执行的代码，直接调用，相当于普通方法的调用

    start()：启动线程；然后由JVM调用此线程的run()方法

<font color=blue>**2. 实现Runnable接口**</font>

- **Thread构造方法**

  | 方法名                               | 说明                   |
  | ------------------------------------ | ---------------------- |
  | Thread(Runnable target)              | 分配一个新的Thread对象 |
  | Thread(Runnable target, String name) | 分配一个新的Thread对象 |

- **实现步骤**

  - 定义一个类MyRunnable<font color=red>**实现Runnable接口**</font>
  - 在MyRunnable类中<font color=red>**重写run()方法**</font>
  - <font color=red>**创建MyRunnable类的对象**</font>
  - <font color=red>**创建Thread类的对象，把MyRunnable对象作为构造方法的参数**</font>
  - <font color=red>**启动线程**</font>

- **代码演示**

  ```java
  public class MyRunnable implements Runnable {
      @Override
      public void run() {
          //书写要执行的代码
          for(int i=0; i<100; i++) {
              //不可直接用Thread中的getName方法，因为没继承
              //使用Thread.currentThread()方法，获取正在执行的线程
              System.out.println(Thread.currentThread().getName()+":"+i);
          }
      }
  }
  public class MyRunnableDemo {
      public static void main(String[] args) {
          //创建MyRunnable类的对象
          MyRunnable my = new MyRunnable();
  
          //创建Thread类的对象，把MyRunnable对象作为构造方法的参数
          Thread t1 = new Thread(my,"坦克");
          Thread t2 = new Thread(my,"飞机");
  
          //启动线程
          t1.start();
          t2.start();
      }
  }
  ```

<font color=blue>**3. 实现Callable接口和Future接口**</font>

+ **特点**：<font color=red>**可以获取到多线程运行的结果**</font>

+ **方法介绍**

  | 方法名                           | 说明                                               |
  | -------------------------------- | -------------------------------------------------- |
  | V call()                         | 计算结果，如果无法计算结果，则抛出一个异常         |
  | FutureTask(Callable<V> callable) | 创建一个 FutureTask，一旦运行就执行给定的 Callable |
  | V get()                          | 如有必要，等待计算完成，然后获取其结果             |

+ **实现步骤**

  + 定义一个类MyCallable**实现Callable接口**
  + 在MyCallable类中**重写call()方法**(此方法有返回值，<font color=red>**即多线程运行的结果**</font>)
  + **创建MyCallable类的对象**(<font color=red>**即多线程要执行的任务**</font>)
  + 创建Future实现类**FutureTask对象**，把MyCallable对象作为构造方法的参数(<font color=red>**即管理多线程运行的结果**</font>)
  + **创建Thread类的对象**，把FutureTask对象作为构造方法的参数(<font color=red>**即表示线程**</font>)
  + **启动线程**
  + 再**调用get方法**，就可以获取线程结束之后的结果

+ **代码演示**

  ```java
  // implements Callable<V> 泛型指代运行结果的类型
  public class MyCallable implements Callable<String> {
      @Override
      public String call() throws Exception {
          for (int i = 0; i < 100; i++) {
              System.out.println("跟女孩表白" + i);
          }
          //返回值就表示线程运行完毕之后的结果
          return "答应";
      }
  }
  
  public class Demo {
      public static void main(String[] args) throws ExecutionException, InterruptedException {
          //创建MyCallable对象(表示线程要执行的任务)
          MyCallable mc = new MyCallable();
          //创建FutureTask对象(作用管理多线程运行的结果)
          //可以获取线程执行完毕之后的结果.也可以作为参数传递给Thread对象
          FutureTask<String> ft = new FutureTask<>(mc);
          //创建线程对象
          Thread t1 = new Thread(ft);
          //获取多线程运行的结果
          String s = ft.get();
          //开启线程
          t1.start();
  
          //String s = ft.get();
          System.out.println(s);
      }
  }
  ```

<font color=blue>**4. 三种实现方式对比**</font>

+ 实现Runnable、Callable接口
  + 好处: 扩展性强，实现该接口的同时还可以继承其他的类
  + 缺点: 编程相对复杂，不能直接使用Thread类中的方法
+ 继承Thread类
  + 好处: 编程比较简单，可以直接使用Thread类中的方法
  + 缺点: 可以扩展性较差，不能再继承其他的类



### 1.3 多线程成员方法

<font color=blue>**常见的成员方法：**</font>

| 方法名称                      | 说明                           |
| ----------------------------- | ------------------------------ |
| getName()                     | 返回此线程名称                 |
| setName(String name)          | 设置此线程名称                 |
| static Thread currentThread() | 获取当前线程对象               |
| static void sleep(long time)  | 让线程休眠指定时间，单位为毫秒 |
| setPriority(int newPriority)  | 设置线程优先级                 |
| getPriority()                 | 获取线程优先级                 |
| setDaemon(boolean on)         | 设置为守护线程                 |
| yield()                       | 出让线程/礼让线程              |
| join()                        | 插入线程/插队线程              |

#### 1.3.1 设置和获取线程名称

<font color=blue>**1. 方法介绍**</font>

| 方法名                     | 说明                               |
| -------------------------- | ---------------------------------- |
| void  setName(String name) | 将此线程的名称更改为等于参数name   |
| String  getName()          | 返回此线程的名称                   |
| Thread  currentThread()    | 返回对当前正在执行的线程对象的引用 |

<font color=blue>**2. 代码演示**</font>

```java
public class MyThread extends Thread {
    public MyThread() {}
    public MyThread(String name) {
        super(name); //需要继承父类的构造，才能使用setName方法
    }

    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.println(getName()+":"+i);
        }
    }
}
public class MyThreadDemo {
    public static void main(String[] args) {
        MyThread my1 = new MyThread();
        MyThread my2 = new MyThread();
        my1.setName("高铁");
        my2.setName("飞机");

        MyThread my1 = new MyThread("高铁");
        MyThread my2 = new MyThread("飞机");

        my1.start();
        my2.start();

        System.out.println(Thread.currentThread().getName());
    }
}
```

<font color=blue>**3. 细节**</font>

- 如果未给线程设置名字，线程也有默认名字
  - 格式：<font color=red>**Thread-X**</font> (X序号，从0开始)
- 若给线程设置名字，可用set方法，也可用构造方法
- currentThread()方法，当JVM虚拟机启动后，会自动启动多条线程，其中一条为main线程，作用是调用main方法，并执行里面的代码。之前写的所有代码都是运行在main线程中

#### 1.3.2 线程休眠

<font color=blue>**1. 相关方法**</font>

| 方法名                         | 说明                                             |
| ------------------------------ | ------------------------------------------------ |
| static void sleep(long millis) | 使当前正在执行的线程停留（暂停执行）指定的毫秒数 |

**细节**：

- 哪条线程执行到此方法，这条线程便会停留对应时间
- 方法的参数：表示睡眠时间，单位为毫秒

<font color=blue>**2. 代码演示**</font>

```java
public class MyRunnable implements Runnable {
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            try {
                Thread.sleep(100); //循环中睡眠，每次循环停留一秒
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println(Thread.currentThread().getName() + "---" + i);
        }
    }
}
public class Demo {
    public static void main(String[] args) throws InterruptedException {
        /*System.out.println("睡觉前");
        Thread.sleep(3000);
        System.out.println("睡醒了");*/

        MyRunnable mr = new MyRunnable();

        Thread t1 = new Thread(mr);
        Thread t2 = new Thread(mr);

        t1.start();
        t2.start();
    }
}
```

#### 1.3.3 线程优先级

<font color=blue>**1. 线程的两种调度方式**</font>

- **分时调度模型**：所有线程<font color=red>**轮流**</font>使用 CPU 的使用权，平均分配每个线程占用 CPU 的时间片
- **抢占式调度模型**：优先让优先级高的线程使用 CPU，如果线程的优先级相同，那么会<font color=red>**随机**</font>选择一个，优先级高的线程获取的 CPU 时间片相对多一些(<font color=red>**Java使用**</font>)

==**注意**==：优先级越高，只能代表抢到CPU的<font color=red>**概率更大**</font>，不能保障一定抢到

<font color=blue>**2. 优先级相关代码**</font>

| 方法名                                  | 说明                                                         |
| --------------------------------------- | ------------------------------------------------------------ |
| final int getPriority()                 | 返回此线程的优先级                                           |
| final void setPriority(int newPriority) | 更改此线程的优先级线程；**默认优先级是5**；线程优先级的范围是：1-10 |

<font color=blue>**3. 代码演示**</font>

```java
public class MyCallable implements Callable<String> {
    @Override
    public String call() throws Exception {
        for (int i = 0; i < 100; i++) {
            System.out.println(Thread.currentThread().getName() + "---" + i);
        }
        return "线程执行完毕了";
    }
}
public class Demo {
    public static void main(String[] args) {
        //优先级: 1 - 10 默认值:5
        MyCallable mc = new MyCallable();

        FutureTask<String> ft = new FutureTask<>(mc);

        Thread t1 = new Thread(ft);
        t1.setName("飞机");
        t1.setPriority(10);
        //System.out.println(t1.getPriority());//5
        t1.start();

        MyCallable mc2 = new MyCallable();

        FutureTask<String> ft2 = new FutureTask<>(mc2);

        Thread t2 = new Thread(ft2);
        t2.setName("坦克");
        t2.setPriority(1);
        //System.out.println(t2.getPriority());//5
        t2.start();
    }
}
```

#### 1.3.4 守护线程

<font color=blue>**1. 相关方法**</font>

| 方法名                     | 说明                                                         |
| -------------------------- | ------------------------------------------------------------ |
| void setDaemon(boolean on) | 将此线程标记为守护线程，当运行的线程都是守护线程时，Java虚拟机将退出 |

==细节==：当其他非守护线程执行完毕，守护线程也会陆续结束

应用场景：qq聊天，当线程1聊天结束，线程2传输文件便会关闭

<font color=blue>**2. 代码演示**</font>

```java
public class MyThread1 extends Thread {
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println(getName() + "---" + i);
        }
    }
}
public class MyThread2 extends Thread {
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            System.out.println(getName() + "---" + i);
        }
    }
}
public class Demo {
    public static void main(String[] args) {
        MyThread1 t1 = new MyThread1();
        MyThread2 t2 = new MyThread2();

        t1.setName("女神");
        t2.setName("备胎");

        //把第二个线程设置为守护线程
        //当普通线程执行完之后,那么守护线程也没有继续运行下去的必要了.
        t2.setDaemon(true);

        t1.start();
        t2.start();
    }
}
```



### 1.4 线程安全问题

#### 1.4.1 安全问题场景

<font color=blue>**1. 卖票案例**</font>

- **案例需求**

  某电影院目前正在上映国产大片，共有100张票，而它有3个窗口卖票，请设计一个程序模拟该电影院卖票

- **实现步骤**

  - 定义一个类SellTicket实现Runnable接口，里面定义一个成员变量：private int tickets = 100;

  - 在SellTicket类中重写run()方法实现卖票，代码步骤如下

  - 判断票数大于0，就卖票，并告知是哪个窗口卖的
  - 卖了票之后，总票数要减1
  - 票卖没了，线程停止
  - 定义一个测试类SellTicketDemo，里面有main方法，代码步骤如下
  - 创建SellTicket类的对象
  - 创建三个Thread类的对象，把SellTicket对象作为构造方法的参数，并给出对应的窗口名称
  - 启动线程

- **代码实现**

  ```java
  public class SellTicket implements Runnable {
   
      private int ticket = 100;
  
      //在SellTicket类中重写run()方法实现卖票，代码步骤如下
      @Override
      public void run() {
          while (true) {
              if(ticket <= 0){
                      //卖完了
                      break;
                  }else{
                      try {
                          Thread.sleep(100);
                      } catch (InterruptedException e) {
                          e.printStackTrace();
                      }
                      ticket--;
                      System.out.println(Thread.currentThread().getName() + "在卖票,还剩下" + ticket + "张票");
                  }
          }
      }
  }
  public class SellTicketDemo {
      public static void main(String[] args) {
          //创建SellTicket类的对象
          SellTicket st = new SellTicket();
  
          //创建三个Thread类的对象，把SellTicket对象作为构造方法的参数，并给出对应的窗口名称
          Thread t1 = new Thread(st,"窗口1");
          Thread t2 = new Thread(st,"窗口2");
          Thread t3 = new Thread(st,"窗口3");
  
          //启动线程
          t1.start();
          t2.start();
          t3.start();
      }
  }
  ```

<font color=blue>**2. 卖票案例引发的安全问题**</font>

- 相同的票出现了多次
- 出现了负数的票

- 问题产生原因

  **线程执行的随机性导致的**,可能在卖票过程中丢失cpu的执行权,导致出现问题

#### 1.4.2 同步代码块

<font color=blue>**1. 安全问题出现的条件**</font>

- 是多线程环境
- 有共享数据
- 有多条语句操作共享数据

<font color=blue>**2. 如何解决多线程安全问题？**</font>

- 基本思想：<font color=red>**让程序没有安全问题的环境**</font>
- 怎么实现呢?
  - **把多条语句操作共享数据的代码给锁起来**，让任意时刻只能有一个线程执行即可
  - Java提供了同步代码块的方式来解决

<font color=blue>**3. 同步代码块格式**</font>

```java
synchronized(锁) {  // 相当于给代码加锁，任意对象看成一把锁
	多条语句操作共享数据的代码 
}
```

- **特点1**：锁默认打开，<font color=red>**有一个线程进去，锁自动关闭**</font>
- **特点2**：里面代码全部执行完毕，<font color=red>**线程出来，锁自动打开**</font>

<font color=blue>**4. 同步好处和弊端**</font>

- 好处：解决了多线程的数据安全问题

- 弊端：线程很多时，因为每个线程都会去判断同步上的锁，这是很耗费资源的，无形中会降低程序的运行效率

<font color=blue>**5. 代码演示**</font>

```java
public class SellTicket implements Runnable {
    private int tickets = 100;
    private Object obj = new Object();

    @Override
    public void run() {
        while (true) {
          //细节1：同步代码块不能写在循环外面，不然会导致1个线程卖完所有票
          //细节2：锁对象一定唯一，一般写成当前类的字节码文件，例如synchronized (SellTicket.class) 
            synchronized (obj) { // 对可能有安全问题的代码加锁,多个线程必须使用同一把锁
                //t1进来后，就会把这段代码给锁起来
                if (tickets > 0) {
                    try {
                        Thread.sleep(100);
                        //t1休息100毫秒
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    //窗口1正在出售第100张票
                    System.out.println(Thread.currentThread().getName() + "正在出售第" + tickets + "张票");
                    tickets--; //tickets = 99;
                }
            }
            //t1出来了，这段代码的锁就被释放了
        }
    }
}

public class SellTicketDemo {
    public static void main(String[] args) {
        SellTicket st = new SellTicket();

        Thread t1 = new Thread(st, "窗口1");
        Thread t2 = new Thread(st, "窗口2");
        Thread t3 = new Thread(st, "窗口3");

        t1.start();
        t2.start();
        t3.start();
    }
}
```

#### 1.4.3 同步方法

<font color=blue>**1. 同步方法格式**</font>

同步方法：就是把synchronized关键字加到方法上

```java
修饰符 synchronized 返回值类型 方法名(方法参数) { 
	方法体；
}
```

- 特点1：同步方法是锁住方法里面的代码
- 特点2：**锁对象不能自己指定**
  - 非静态：<font color=red>**this**</font>(当前对象的调用者)
  - 静态：<font color=red>**当前类的字节码文件对象   类名.class**</font>

<font color=blue>**2. 代码演示**</font>

```java
public class MyRunnable implements Runnable {
    //加上static，表示这个类所有对象都共享ticket数据
    private static int ticketCount = 100;

    @Override
    public void run() {
        while(true){
            if("窗口一".equals(Thread.currentThread().getName())){
                //同步方法
                boolean result = synchronizedMthod();
                if(result){
                    break;
                }
            }

            if("窗口二".equals(Thread.currentThread().getName())){
                //同步代码块
                synchronized (MyRunnable.class){
                    if(ticketCount == 0){
                       break;
                    }else{
                        try {
                            Thread.sleep(10);
                        } catch (InterruptedException e) {
                            e.printStackTrace();
                        }
                        ticketCount--;
                        System.out.println(Thread.currentThread().getName() + "在卖票,还剩下" + ticketCount + "张票");
                    }
                }
            }

        }
    }

    private static synchronized boolean synchronizedMthod() {
        if(ticketCount == 0){
            return true;
        }else{
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            ticketCount--;
            System.out.println(Thread.currentThread().getName() + "在卖票,还剩下" + ticketCount + "张票");
            return false;
        }
    }
}

 public class Demo {
      public static void main(String[] args) {
          MyRunnable mr = new MyRunnable();
          Thread t1 = new Thread(mr);
      	  Thread t2 = new Thread(mr);

          t1.setName("窗口一");
          t2.setName("窗口二");

          t1.start();
          t2.start();
      }
}
```


 <font color=blue>**3. StringBuilder与StringBuffer区别**</font>

- StringBuilder的实例用于多个线程是不安全的，如需同步，建议使用StringBuffer
- **选择方式**：代码是单线程，不需要考虑数据安全，用StringBuilder，若为多线程环境用StringBuffer



#### 1.4.4 Lock锁

 <font color=blue>**1. Lock锁概念**</font>

更清楚表达如何加锁和释放锁，JDK5之后提供一个新的锁对象lock

- Lock实现比synchronized方法和语句，获得更广泛的锁定操作
- Lock中提供<font color=red>**手动上锁、手动释放锁**</font>

 <font color=blue>**2. Lock是接口，需采用实现类ReentrantLock实例化**</font>

| 方法名          | 说明                        |
| --------------- | --------------------------- |
| ReentrantLock() | 创建一个ReentrantLock的实例 |

 <font color=blue>**3. 加锁解析方法**</font>

| 方法名        | 说明   |
| ------------- | ------ |
| void lock()   | 获得锁 |
| void unlock() | 释放锁 |

**代码演示**

```java
 public class Ticket implements Runnable {
      //票的数量
      private int ticket = 100;
      private Object obj = new Object();
      private ReentrantLock lock = new ReentrantLock();

      @Override
      public void run() {
          while (true) {
              //synchronized (obj){//多个线程必须使用同一把锁.
              try {
                  lock.lock();
                  if (ticket <= 0) {
                      //卖完了
                      break;
                  } else {
                      Thread.sleep(100);
                      ticket--;
                      System.out.println(Thread.currentThread().getName() + "在卖票,还剩下" + ticket + "张票");
                  }
              } catch (InterruptedException e) {
                  e.printStackTrace();
              } finally {
                  lock.unlock();
              }
              // }
          }
      }
  }

  public class Demo {
      public static void main(String[] args) {
          Ticket ticket = new Ticket();

          Thread t1 = new Thread(ticket);
          Thread t2 = new Thread(ticket);
          Thread t3 = new Thread(ticket);

          t1.setName("窗口一");
          t2.setName("窗口二");
          t3.setName("窗口三");

          t1.start();
          t2.start();
          t3.start();
      }
  }
```



#### 1.4.5 死锁

 <font color=blue>**1. 死锁是个错误**</font>

**线程死锁**：指由于两个或者多个线程互相持有对方所需要的资源，导致这些线程处于等待状态，无法前往执行

 <font color=blue>**2. 什么情况下会产生死锁**</font>

- 资源有限
- 同步嵌套

**代码演示**

```java
public class Demo {
    public static void main(String[] args) {
        Object objA = new Object();
        Object objB = new Object();

        new Thread(()->{
            while(true){
                synchronized (objA){
                    //线程一
                    synchronized (objB){
                        System.out.println("小康同学正在走路");
                    }
                }
            }
        }).start();

        new Thread(()->{
            while(true){
                synchronized (objB){
                    //线程二
                    synchronized (objA){
                        System.out.println("小薇同学正在走路");
                    }
                }
            }
        }).start();
    }
}
```



### 1.5 等待唤醒机制

#### 1.5.1 生产者和消费者模式

 <font color=blue>**1. 概述**</font>

- 生产者消费者模式：十分经典的多线程协作模式
- 包含两类线程：
  - **生产者线程**：用于生产数据
  - **消费者线程**：用于消费数据
- 共享的数据区域：为解耦生产者和消费者关系
  - 生产者生产数据之后：直接放置在共享数据区域中，并不需要关心消费者行为
  - 消费者获取数据：从共享区域中获取数据，并不需要关心生产者行为

 <font color=blue>**2. Object类的等待唤醒方法**</font>

| 方法名           | 说明                                                         |
| ---------------- | ------------------------------------------------------------ |
| void wait()      | 导致当前线程等待，直到另一个线程调用该对象的 notify()方法或 notifyAll()方法 |
| void notify()    | 唤醒正在等待对象监视器的单个线程                             |
| void notifyAll() | 唤醒正在等待对象监视器的所有线程                             |

 <font color=blue>**3. 生产者和消费者案例**</font>

- **案例需求**

  + 桌子类(Desk)：定义表示包子数量的变量,定义锁对象变量,定义标记桌子上有无包子的变量

  + 生产者类(Cooker)：实现Runnable接口，重写run()方法，设置线程任务

    1.判断是否有包子,决定当前线程是否执行

    2.如果有包子,就进入等待状态,如果没有包子,继续执行,生产包子

    3.生产包子之后,更新桌子上包子状态,唤醒消费者消费包子

  + 消费者类(Foodie)：实现Runnable接口，重写run()方法，设置线程任务

    1.判断是否有包子,决定当前线程是否执行

    2.如果没有包子,就进入等待状态,如果有包子,就消费包子

    3.消费包子后,更新桌子上包子状态,唤醒生产者生产包子

  + 测试类(Demo)：里面有main方法，main方法中的代码步骤如下

    创建生产者线程和消费者线程对象

    分别开启两个线程

- **代码实现**

  ```java
  // 控制生产者和消费者的执行
  public class Desk {
      //定义一个标记，0：没有面条，1：有面条  
      public static int flag = 0; //用boolean也行，只是boolean只能控制两条线程
      //汉堡包的总数量
      public static int count = 10;
      //锁对象
      public static final Object lock = new Object();
  }
  ```
  
  ```java
  public class Foodie extends Thread {
      @Override
      public void run() {
  //        1，判断桌子上是否有汉堡包。
  //        2，如果没有就等待。
  //        3，如果有就开吃
  //        4，吃完之后，桌子上的汉堡包就没有了
  //                叫醒等待的生产者继续生产
  //        汉堡包的总数量减一
  
          //套路:
              //1. while(true)死循环
              //2. synchronized 锁,锁对象要唯一
              //3. 判断,共享数据是否结束. 结束
              //4. 判断,共享数据是否结束. 没有结束
          while(true){
              synchronized (Desk.lock){
                  if(Desk.count == 0){ //吃完了，即到了末尾
                      break;
                  }else{
                      if(Desk.flag == 0){
                          //有
                          System.out.println("吃货在吃汉堡包");
                          Desk.flag = 1;
                          Desk.lock.notifyAll();//唤醒跟这把锁绑定的所有线程
                          Desk.count--;
                      }else{
                          //没有就等待
                          //使用什么对象当做锁,那么就必须用这个对象去调用等待和唤醒的方法.
                          try {
                              Desk.lock.wait();//让当前线程与锁进行绑定
                          } catch (InterruptedException e) {
                              e.printStackTrace();
                          }
                      }
                  }
              }
          }
      }
  }
  ```
  
  ```java
  public class Cooker extends Thread {
  //    生产者步骤：
  //            1，判断桌子上是否有汉堡包
  //    如果有就等待，如果没有才生产。
  //            2，把汉堡包放在桌子上。
  //            3，叫醒等待的消费者开吃。
      @Override
      public void run() {
          while(true){
              synchronized (Desk.lock){
                  if(Desk.count == 0){ 
                      break;
                  }else{
                      if(Desk.flag==1){
                          //生产
                          System.out.println("厨师正在生产汉堡包");
                          Desk.flag = true;
                          Desk.lock.notifyAll();
                      }else{
                          try {
                              Desk.lock.wait();
                          } catch (InterruptedException e) {
                              e.printStackTrace();
                          }
                      }
                  }
              }
          }
      }
  }
  ```
  
  ```java
  
  public class Demo {
      public static void main(String[] args) {
          /*消费者步骤：
          1，判断桌子上是否有汉堡包。
          2，如果没有就等待。
          3，如果有就开吃
          4，吃完之后，桌子上的汉堡包就没有了
                  叫醒等待的生产者继续生产
          汉堡包的总数量减一*/
  
          /*生产者步骤：
          1，判断桌子上是否有汉堡包
          如果有就等待，如果没有才生产。
          2，把汉堡包放在桌子上。
          3，叫醒等待的消费者开吃。*/
  
          Foodie f = new Foodie();
          Cooker c = new Cooker();
  
          f.start();
          c.start();
      }
  }
  ```

 <font color=blue>**4. 生产者和消费者案例优化**</font>

+ **需求**

  + 将Desk类中的变量,采用面向对象的方式封装起来
  + 生产者和消费者类中构造方法接收Desk类对象,之后在run方法中进行使用
  + 创建生产者和消费者线程对象,构造方法中传入Desk类对象
  + 开启两个线程

+ **代码实现**

  ```java
  public class Desk {
  
      //定义一个标记
      //true 就表示桌子上有汉堡包的,此时允许吃货执行
      //false 就表示桌子上没有汉堡包的,此时允许厨师执行
      //public static boolean flag = false;
      private boolean flag;
  
      //汉堡包的总数量
      //public static int count = 10;
      //以后我们在使用这种必须有默认值的变量
     // private int count = 10;
      private int count;
  
      //锁对象
      //public static final Object lock = new Object();
      private final Object lock = new Object();
  
      public Desk() {
          this(false,10); // 在空参内部调用带参,对成员变量进行赋值,之后就可以直接使用成员变量了
      }
  
      public Desk(boolean flag, int count) {
          this.flag = flag;
          this.count = count;
      }
  
      public boolean isFlag() {
          return flag;
      }
  
      public void setFlag(boolean flag) {
          this.flag = flag;
      }
  
      public int getCount() {
          return count;
      }
  
      public void setCount(int count) {
          this.count = count;
      }
  
      public Object getLock() {
          return lock;
      }
  
      @Override
      public String toString() {
          return "Desk{" +
                  "flag=" + flag +
                  ", count=" + count +
                  ", lock=" + lock +
                  '}';
      }
  }
  ```
  
  ```java
  public class Cooker extends Thread {
  
      private Desk desk;
  
      public Cooker(Desk desk) {
          this.desk = desk;
      }
  //    生产者步骤：
  //            1，判断桌子上是否有汉堡包
  //    如果有就等待，如果没有才生产。
  //            2，把汉堡包放在桌子上。
  //            3，叫醒等待的消费者开吃。
  
      @Override
      public void run() {
          while(true){
              synchronized (desk.getLock()){
                  if(desk.getCount() == 0){
                      break;
                  }else{
                      //System.out.println("验证一下是否执行了");
                      if(!desk.isFlag()){
                          //生产
                          System.out.println("厨师正在生产汉堡包");
                          desk.setFlag(true);
                          desk.getLock().notifyAll();
                      }else{
                          try {
                              desk.getLock().wait();
                          } catch (InterruptedException e) {
                              e.printStackTrace();
                          }
                      }
                  }
              }
          }
      }
  }
  ```
  
  ```java
  public class Foodie extends Thread {
      private Desk desk;
  
      public Foodie(Desk desk) {
          this.desk = desk;
      }
  
      @Override
      public void run() {
  //        1，判断桌子上是否有汉堡包。
  //        2，如果没有就等待。
  //        3，如果有就开吃
  //        4，吃完之后，桌子上的汉堡包就没有了
  //                叫醒等待的生产者继续生产
  //        汉堡包的总数量减一
  
          //套路:
              //1. while(true)死循环
              //2. synchronized 锁,锁对象要唯一
              //3. 判断,共享数据是否结束. 结束
              //4. 判断,共享数据是否结束. 没有结束
          while(true){
              synchronized (desk.getLock()){
                  if(desk.getCount() == 0){
                      break;
                  }else{
                      //System.out.println("验证一下是否执行了");
                      if(desk.isFlag()){
                          //有
                          System.out.println("吃货在吃汉堡包");
                          desk.setFlag(false);
                          desk.getLock().notifyAll();
                          desk.setCount(desk.getCount() - 1);
                      }else{
                          //没有就等待
                          //使用什么对象当做锁,那么就必须用这个对象去调用等待和唤醒的方法.
                          try {
                              desk.getLock().wait();
                          } catch (InterruptedException e) {
                              e.printStackTrace();
                          }
                      }
                  }
              }
          }
      }
  }
  ```
  
  ```java
  public class Demo {
      public static void main(String[] args) {
          /*消费者步骤：
          1，判断桌子上是否有汉堡包。
          2，如果没有就等待。
          3，如果有就开吃
          4，吃完之后，桌子上的汉堡包就没有了
                  叫醒等待的生产者继续生产
          汉堡包的总数量减一*/
  
          /*生产者步骤：
          1，判断桌子上是否有汉堡包
          如果有就等待，如果没有才生产。
          2，把汉堡包放在桌子上。
          3，叫醒等待的消费者开吃。*/
  
          Desk desk = new Desk();
  
          Foodie f = new Foodie(desk);
          Cooker c = new Cooker(desk);
  
          f.start();
          c.start();
  
      }
  }
  ```

#### 1.5.2 阻塞队列的基本使用

 <font color=blue>**1. 阻塞队列的继承结构**</font>

![06_阻塞队列继承结构](javaBasis_assets\06_阻塞队列继承结构.png)


+ 常见BlockingQueue:

  - ArrayBlockingQueue: 底层是数组,有界

  - LinkedBlockingQueue: 底层是链表,无界.但不是真正的无界,最大为int的最大值

 <font color=blue>**2. BlockingQueue的核心方法**</font>

**put(anObject)**: 将参数放入队列,如果放不进去会阻塞

**take()**: 取出第一个数据,取不到会阻塞

 <font color=blue>**3. 代码示例**</font>

```java
public class Demo02 {
    public static void main(String[] args) throws Exception {
        // 在测试类中创建阻塞队列的对象,容量为 1，这可以保证生产者消费者用同一条
        ArrayBlockingQueue<String> arrayBlockingQueue = new ArrayBlockingQueue<>(1);

        // 存储元素
        arrayBlockingQueue.put("汉堡包");

        // 取元素
        System.out.println(arrayBlockingQueue.take());
        System.out.println(arrayBlockingQueue.take()); // 取不到会阻塞
        System.out.println("程序结束了");
    }
}
```

#### 1.5.3 阻塞队列实现等待唤醒机制

+ **案例需求**

  + 生产者类(Cooker)：实现Runnable接口，重写run()方法，设置线程任务

    1.构造方法中接收一个阻塞队列对象

    2.在run方法中循环向阻塞队列中添加包子

    3.打印添加结果

  + 消费者类(Foodie)：实现Runnable接口，重写run()方法，设置线程任务

    1.构造方法中接收一个阻塞队列对象

    2.在run方法中循环获取阻塞队列中的包子

    3.打印获取结果

  + 测试类(Demo)：里面有main方法，main方法中的代码步骤如下

    创建阻塞队列对象

    创建生产者线程和消费者线程对象,构造方法中传入阻塞队列对象

    分别开启两个线程

+ **代码实现**

  ```java
  public class Cooker extends Thread {
  
      private ArrayBlockingQueue<String> bd;
  
      public Cooker(ArrayBlockingQueue<String> bd) {
          this.bd = bd;
      }
  
      @Override
      public void run() {
          while (true) {
              try {
                  bd.put("汉堡包");
                  System.out.println("厨师放入一个汉堡包");
              } catch (InterruptedException e) {
                  e.printStackTrace();
              }
          }
      }
  }
  
  public class Foodie extends Thread {
      private ArrayBlockingQueue<String> bd;
  
      public Foodie(ArrayBlockingQueue<String> bd) {
          this.bd = bd;
      }
  
      @Override
      public void run() {
          while (true) {
              try {
                  String take = bd.take();
                  System.out.println("吃货将" + take + "拿出来吃了");
              } catch (InterruptedException e) {
                  e.printStackTrace();
              }
          }
  
      }
  }
  
  public class Demo {
      public static void main(String[] args) {
          ArrayBlockingQueue<String> bd = new ArrayBlockingQueue<>(1);
  
          Foodie f = new Foodie(bd);
          Cooker c = new Cooker(bd);
  
          f.start();
          c.start();
      }
  }
  ```



### 1.6 线程池

#### 1.6.1 线程状态介绍

当线程被创建并启动以后，它既不是一启动就进入了执行状态，也不是一直处于执行状态。线程对象在不同的时期有不同的状态。那么Java中的线程存在哪几种状态呢？Java中的线程

状态被定义在了java.lang.Thread.State枚举类中，State枚举类的源码如下：

```java
public class Thread { 
    public enum State {
    
        /* 新建 */
        NEW , 

        /* 可运行状态 */
        RUNNABLE , 

        /* 阻塞状态 */
        BLOCKED , 

        /* 无限等待状态 */
        WAITING , 

        /* 计时等待 */
        TIMED_WAITING , 

        /* 终止 */
        TERMINATED;  
	}
    
    // 获取当前线程的状态
    public State getState() {
        return jdk.internal.misc.VM.toThreadState(threadStatus);
    }  
}
```

通过源码可以看到Java中的线程存在6种状态，每种线程状态的含义如下

| 线程状态      | 具体含义                                                     |
| ------------- | ------------------------------------------------------------ |
| NEW           | 一个尚未启动的线程的状态。也称之为初始状态、开始状态。线程刚被创建，但是并未启动。还没调用start方法。MyThread t = new MyThread()只有线程象，没有线程特征。 |
| RUNNABLE      | 当我们调用线程对象的start方法，那么此时线程对象进入了RUNNABLE状态。那么此时才是真正的在JVM进程中创建了一个线程，线程一经启动并不是立即得到执行，线程的运行与否要听令与CPU的调度，那么我们把这个中间状态称之为可执行状态(RUNNABLE)也就是说它具备执行的资格，但是并没有真正的执行起来而是在等待CPU的度。 |
| BLOCKED       | 当一个线程试图获取一个对象锁，而该对象锁被其他的线程持有，则该线程进入Blocked状态；当该线程持有锁时，该线程将变成Runnable状态。 |
| WAITING       | 一个正在等待的线程的状态。也称之为等待状态。造成线程等待的原因有两种，分别是调用Object.wait()、join()方法。处于等待状态的线程，正在等待其他线程去执行一个特定的操作。例如：因为wait()而等待的线程正在等待另一个线程去调用notify()或notifyAll()；一个因为join()而等待的线程正在等待另一个线程结束。 |
| TIMED_WAITING | 一个在限定时间内等待的线程的状态。也称之为限时等待状态。造成线程限时等待状态的原因有三种，分别是：Thread.sleep(long)，Object.wait(long)、join(long)。 |
| TERMINATED    | 一个完全运行完成的线程的状态。也称之为终止状态、结束状态     |

各个状态的转换，如下图所示：

![1591163781941](javaBasis_assets\1591163781941.png)

#### 1.6.2 线程池的基本使用

<font color=blue>**1. 线程池的意义**</font>

​	系统创建一个线程的成本是比较高的，因为它涉及到与操作系统交互，当程序中需要创建大量生存期很短暂的线程时，频繁的创建和销毁线程对系统的资源消耗有可能大于业务处理是对系统资源的消耗，这样就有点"舍本逐末"了。针对这一种情况，为了提高性能，我们就可以采用线程池。线程池在启动的时，会创建大量空闲线程，当我们向线程池提交任务的时，线程池就会启动一个线程来执行该任务。等待任务执行完毕以后，线程并不会死亡，而是再次返回到线程池中称为空闲状态。等待下一次任务的执行。

<font color=blue>**2. 线程池的设计思路**</font>

1. 准备一个任务容器
2. 一次性启动多个(2个)消费者线程
3. 刚开始任务容器是空的，所以线程都在wait
4. 直到一个外部线程向这个任务容器中扔了一个"任务"，就会有一个消费者线程被唤醒
5. 这个消费者线程取出"任务"，并且执行这个任务，执行完毕后，继续等待下一次任务的到来

<font color=blue>**3. 创建线程池---Executors默认线程池**</font>

JDK对线程池进行了相关的实现，在真实企业开发中也很少去自定义线程池，而是使用JDK中自带的线程池。

Executors：线程池的工具类**通过调用方法**返回不同类型的线程池对象

使用Executors中所提供的**静态**方法来创建线程池：

| 方法名称                                     | 说明                                         |
| -------------------------------------------- | -------------------------------------------- |
| static ExecutorService newCachedThreadPool() | 创建一个没有上限的线程池(默认的线程池)       |
| static newFixedThreadPool(int nThreads)      | 创建有上限的线程池(指定最多线程数量的线程池) |

**代码实现 :** 

```java
package com.itheima.mythreadpool;

//static ExecutorService newCachedThreadPool()   创建一个默认的线程池
//static newFixedThreadPool(int nThreads)	    创建一个指定最多线程数量的线程池

import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class MyThreadPoolDemo {
    public static void main(String[] args) throws InterruptedException {

        //1.创建一个默认的线程池对象.池子中默认是空的.默认最多可以容纳int类型的最大值.
        ExecutorService executorService = Executors.newCachedThreadPool();
        //Executors --- 可以帮助我们创建线程池对象
        //ExecutorService --- 可以帮助我们控制线程池
        
        //2.提交任务
        executorService.submit(()->{
            System.out.println(Thread.currentThread().getName() + "在执行了");
        });

        //Thread.sleep(2000);
        executorService.submit(()->{
            System.out.println(Thread.currentThread().getName() + "在执行了");
        });
        
        //3.销毁线程池
        //executorService.shutdown();
    }
}
```

<font color=blue>**4. 创建线程池---Executors指定上限线程池**</font>

**代码实现 :** 

```java
package com.itheima.mythreadpool;

//static ExecutorService newFixedThreadPool(int nThreads)
//创建一个指定最多线程数量的线程池
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.ThreadPoolExecutor;

public class MyThreadPoolDemo2 {
    public static void main(String[] args) {
        //参数不是初始值而是最大值
        ExecutorService executorService = Executors.newFixedThreadPool(10);

        ThreadPoolExecutor pool = (ThreadPoolExecutor) executorService;
        System.out.println(pool.getPoolSize());//0

        executorService.submit(()->{
            System.out.println(Thread.currentThread().getName() + "在执行了");
        });

        executorService.submit(()->{
            System.out.println(Thread.currentThread().getName() + "在执行了");
        });

        System.out.println(pool.getPoolSize());//2
//        executorService.shutdown();
    }
}
```

<font color=blue>**5. 创建线程池对象---ThreadPoolExecutor**</font>

ThreadPoolExecutor threadPoolExecutor = new ThreadPoolExecutor(核心线程数量,最大线程数量,空闲线程最大存活时间,任务队列,创建线程工厂,任务的拒绝策略);

**代码实现 :** 

```java
package com.itheima.mythreadpool;

import java.util.concurrent.ArrayBlockingQueue;
import java.util.concurrent.Executors;
import java.util.concurrent.ThreadPoolExecutor;
import java.util.concurrent.TimeUnit;

public class MyThreadPoolDemo3 {
//    参数一：核心线程数量
//    参数二：最大线程数
//    参数三：空闲线程最大存活时间
//    参数四：时间单位
//    参数五：任务队列
//    参数六：创建线程工厂
//    参数七：任务的拒绝策略
    public static void main(String[] args) {
        ThreadPoolExecutor pool = new ThreadPoolExecutor(2,5,2,TimeUnit.SECONDS,new ArrayBlockingQueue<>(10), Executors.defaultThreadFactory(),new ThreadPoolExecutor.AbortPolicy());
        pool.submit(new MyRunnable());
        pool.submit(new MyRunnable());

        pool.shutdown();
    }
}
```

#### 1.6.3 线程池的参数详解

![1591165506516](javaBasis_assets\1591165506516.png)

```java
public ThreadPoolExecutor(int corePoolSize,
                              int maximumPoolSize,
                              long keepAliveTime,
                              TimeUnit unit,
                              BlockingQueue<Runnable> workQueue,
                              ThreadFactory threadFactory,
                              RejectedExecutionHandler handler)
    
corePoolSize：   核心线程的最大值，不能小于0
maximumPoolSize：最大线程数，不能小于等于0，maximumPoolSize >= corePoolSize
keepAliveTime：  空闲线程最大存活时间,不能小于0
unit：           时间单位
workQueue：      任务队列，不能为null
threadFactory：  创建线程工厂,不能为null      
handler：        任务的拒绝策略,不能为null  
```

#### 1.6.4 线程池的非默认任务拒绝策略

RejectedExecutionHandler是jdk提供的一个任务拒绝策略接口，它下面存在4个子类。

```java
ThreadPoolExecutor.AbortPolicy: 		    丢弃任务并抛出RejectedExecutionException异常。是默认的策略。
ThreadPoolExecutor.DiscardPolicy： 		   丢弃任务，但是不抛出异常 这是不推荐的做法。
ThreadPoolExecutor.DiscardOldestPolicy：    抛弃队列中等待最久的任务 然后把当前任务加入队列中。
ThreadPoolExecutor.CallerRunsPolicy:        调用任务的run()方法绕过线程池直接执行。
```

注：明确线程池对多可执行的任务数 = 队列容量 + 最大线程数

**案例演示1**：演示ThreadPoolExecutor.AbortPolicy任务处理策略

```java
public class ThreadPoolExecutorDemo01 {
    public static void main(String[] args) {

        /**
         * 核心线程数量为1 ， 最大线程池数量为3, 任务容器的容量为1 ,空闲线程的最大存在时间为20s
         */
        ThreadPoolExecutor threadPoolExecutor = new ThreadPoolExecutor(1 , 3 , 20 , TimeUnit.SECONDS ,
                new ArrayBlockingQueue<>(1) , Executors.defaultThreadFactory() , new ThreadPoolExecutor.AbortPolicy()) ;

        // 提交5个任务，而该线程池最多可以处理4个任务，当我们使用AbortPolicy这个任务处理策略的时候，就会抛出异常
        for(int x = 0 ; x < 5 ; x++) {
            threadPoolExecutor.submit(() -> {
                System.out.println(Thread.currentThread().getName() + "---->> 执行了任务");
            });
        }
    }
}
```

**控制台输出结果**

```java
pool-1-thread-1---->> 执行了任务
pool-1-thread-3---->> 执行了任务
pool-1-thread-2---->> 执行了任务
pool-1-thread-3---->> 执行了任务
```

控制台报错，仅仅执行了4个任务，有一个任务被丢弃了



**案例演示2**：演示ThreadPoolExecutor.DiscardPolicy任务处理策略

```java
public class ThreadPoolExecutorDemo02 {
    public static void main(String[] args) {
        /**
         * 核心线程数量为1 ， 最大线程池数量为3, 任务容器的容量为1 ,空闲线程的最大存在时间为20s
         */
        ThreadPoolExecutor threadPoolExecutor = new ThreadPoolExecutor(1 , 3 , 20 , TimeUnit.SECONDS ,
                new ArrayBlockingQueue<>(1) , Executors.defaultThreadFactory() , new ThreadPoolExecutor.DiscardPolicy()) ;

        // 提交5个任务，而该线程池最多可以处理4个任务，当我们使用DiscardPolicy这个任务处理策略的时候，控制台不会报错
        for(int x = 0 ; x < 5 ; x++) {
            threadPoolExecutor.submit(() -> {
                System.out.println(Thread.currentThread().getName() + "---->> 执行了任务");
            });
        }
    }
}
```

**控制台输出结果**

```java
pool-1-thread-1---->> 执行了任务
pool-1-thread-1---->> 执行了任务
pool-1-thread-3---->> 执行了任务
pool-1-thread-2---->> 执行了任务
```

控制台没有报错，仅仅执行了4个任务，有一个任务被丢弃了



**案例演示3**：演示ThreadPoolExecutor.DiscardOldestPolicy任务处理策略

```java
public class ThreadPoolExecutorDemo02 {
    public static void main(String[] args) {
        /**
         * 核心线程数量为1 ， 最大线程池数量为3, 任务容器的容量为1 ,空闲线程的最大存在时间为20s
         */
        ThreadPoolExecutor threadPoolExecutor;
        threadPoolExecutor = new ThreadPoolExecutor(1 , 3 , 20 , TimeUnit.SECONDS ,
                new ArrayBlockingQueue<>(1) , Executors.defaultThreadFactory() , new ThreadPoolExecutor.DiscardOldestPolicy());
        // 提交5个任务
        for(int x = 0 ; x < 5 ; x++) {
            // 定义一个变量，来指定指定当前执行的任务;这个变量需要被final修饰
            final int y = x ;
            threadPoolExecutor.submit(() -> {
                System.out.println(Thread.currentThread().getName() + "---->> 执行了任务" + y);
            });     
        }
    }
}
```

**控制台输出结果**

```java
pool-1-thread-2---->> 执行了任务2
pool-1-thread-1---->> 执行了任务0
pool-1-thread-3---->> 执行了任务3
pool-1-thread-1---->> 执行了任务4
```

由于任务1在线程池中等待时间最长，因此任务1被丢弃。



**案例演示4**：演示ThreadPoolExecutor.CallerRunsPolicy任务处理策略

```java
public class ThreadPoolExecutorDemo04 {
    public static void main(String[] args) {

        /**
         * 核心线程数量为1 ， 最大线程池数量为3, 任务容器的容量为1 ,空闲线程的最大存在时间为20s
         */
        ThreadPoolExecutor threadPoolExecutor;
        threadPoolExecutor = new ThreadPoolExecutor(1 , 3 , 20 , TimeUnit.SECONDS ,
                new ArrayBlockingQueue<>(1) , Executors.defaultThreadFactory() , new ThreadPoolExecutor.CallerRunsPolicy());

        // 提交5个任务
        for(int x = 0 ; x < 5 ; x++) {
            threadPoolExecutor.submit(() -> {
                System.out.println(Thread.currentThread().getName() + "---->> 执行了任务");
            });
        }
    }
}
```

**控制台输出结果**

```java
pool-1-thread-1---->> 执行了任务
pool-1-thread-3---->> 执行了任务
pool-1-thread-2---->> 执行了任务
pool-1-thread-1---->> 执行了任务
main---->> 执行了任务
```

通过控制台的输出，我们可以看到次策略没有通过线程池中的线程执行任务，而是直接调用任务的run()方法绕过线程池直接执行。

## 2. 多线程综合练习

### 练习一：售票

需求：

​	一共有1000张电影票,可以在两个窗口领取,假设每次领取的时间为3000毫秒,

​	请用多线程模拟卖票过程并打印剩余电影票的数量

代码示例：

```java
public class MyThread extends Thread {

    //第一种方式实现多线程，测试类中MyThread会创建多次，所以需要加static
    static int ticket = 1000;

    @Override
    public void run() {
        //1.循环
        while (true) {
            //2.同步代码块
            synchronized (MyThread.class) {
                //3.判断共享数据（已经到末尾）
                if (ticket == 0) {
                    break;
                } else {
                    //4.判断共享数据（没有到末尾）
                    try {
                        Thread.sleep(3000);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    ticket--;
                    System.out.println(getName() + "在卖票，还剩下" + ticket + "张票!!!");
                }
            }
        }
    }
}

public class Test {
    public static void main(String[] args) {
       /*
            一共有1000张电影票,可以在两个窗口领取,假设每次领取的时间为3000毫秒,
            要求:请用多线程模拟卖票过程并打印剩余电影票的数量
        */

        //创建线程对象
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();

        //给线程设置名字
        t1.setName("窗口1");
        t2.setName("窗口2");

        //开启线程
        t1.start();
        t2.start();

    }
}

```



### 练习二：赠送礼物

需求：

​	有100份礼品,两人同时发送，当剩下的礼品小于10份的时候则不再送出。

​	利用多线程模拟该过程并将线程的名字和礼物的剩余数量打印出来.

```java
public class MyRunable implements Runnable {

    //第二种方式实现多线程，测试类中MyRunable只创建一次，所以不需要加static
    int count = 100;

    @Override
    public void run() {
        //1.循环
        while (true) {
            //2.同步代码块
            synchronized (MyThread.class) {
                //3.判断共享数据（已经到末尾）
                if (count < 10) {
                    System.out.println("礼物还剩下" + count + "不再赠送");
                    break;
                } else {
                    //4.判断共享数据（没有到末尾）
                    count--;
                    System.out.println(Thread.currentThread().getName() + "在赠送礼物，还剩下" + count + "个礼物!!!");
                }
            }
        }
    }
}


public class Test {
    public static void main(String[] args) {
        /*
            有100份礼品,两人同时发送，当剩下的礼品小于10份的时候则不再送出，
            利用多线程模拟该过程并将线程的名字和礼物的剩余数量打印出来.
        */

        //创建参数对象
        MyRunable mr = new MyRunable();

        //创建线程对象
        Thread t1 = new Thread(mr,"窗口1");
        Thread t2 = new Thread(mr,"窗口2");

        //启动线程
        t1.start();
        t2.start();
    }
}

```



### 练习三：打印数字

需求：

​	同时开启两个线程，共同获取1-100之间的所有数字。

​	将输出所有的奇数。

```java
public class MyRunable implements Runnable {

    //第二种方式实现多线程，测试类中MyRunable只创建一次，所以不需要加static
    int number = 1;

    @Override
    public void run() {
        //1.循环
        while (true) {
            //2.同步代码块
            synchronized (MyThread.class) {
                //3.判断共享数据（已经到末尾）
                if (number > 100) {
                    break;
                } else {
                    //4.判断共享数据（没有到末尾）
                    if(number % 2 == 1){
                        System.out.println(Thread.currentThread().getName() + "打印数字" + number);
                    }
                    number++;
                }
            }
        }
    }
}


public class Test {
    public static void main(String[] args) {
        /*
           同时开启两个线程，共同获取1-100之间的所有数字。
           要求：将输出所有的奇数。
        */


        //创建参数对象
        MyRunable mr = new MyRunable();

        //创建线程对象
        Thread t1 = new Thread(mr,"线程A");
        Thread t2 = new Thread(mr,"线程B");

        //启动线程
        t1.start();
        t2.start();
    }
}
```

### 练习四：抢红包

需求：

​	抢红包也用到了多线程。

​	假设：100块，分成了3个包，现在有5个人去抢。

​	其中，红包是共享数据。

​	5个人是5条线程。

​	打印结果如下：

​		  XXX抢到了XXX元

​		  XXX抢到了XXX元

 		 XXX抢到了XXX元
 	
 		XXX没抢到
 	
 		XXX没抢到

解决方案一：

```java
public class MyThread extends Thread{

    //共享数据
    //100块，分成了3个包
    static double money = 100;
    static int count = 3;

    //最小的中奖金额
    static final double MIN = 0.01;

    @Override
    public void run() {
        //同步代码块
        synchronized (MyThread.class){
            if(count == 0){
                //判断，共享数据是否到了末尾（已经到末尾）
                System.out.println(getName() + "没有抢到红包！");
            }else{
                //判断，共享数据是否到了末尾（没有到末尾）
                //定义一个变量，表示中奖的金额
                double prize = 0;
                if(count == 1){
                    //表示此时是最后一个红包
                    //就无需随机，剩余所有的钱都是中奖金额
                    prize = money;
                }else{
                    //表示第一次，第二次（随机）
                    Random r = new Random();
                    //100 元   3个包
                    //第一个红包：99.98
                    //100 - (3-1) * 0.01
                    double bounds = money - (count - 1) * MIN;
                    prize = r.nextDouble(bounds);
                    if(prize < MIN){
                        prize = MIN;
                    }
                }
                //从money当中，去掉当前中奖的金额
                money = money - prize;
                //红包的个数-1
                count--;
                //本次红包的信息进行打印
                System.out.println(getName() + "抢到了" + prize + "元");
            }
        }
    }
}
public class Test {
    public static void main(String[] args) {
        /*
            微信中的抢红包也用到了多线程。
            假设：100块，分成了3个包，现在有5个人去抢。
            其中，红包是共享数据。
            5个人是5条线程。
            打印结果如下：
            	XXX抢到了XXX元
            	XXX抢到了XXX元
            	XXX抢到了XXX元
            	XXX没抢到
            	XXX没抢到
        */

        //创建线程的对象
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();
        MyThread t3 = new MyThread();
        MyThread t4 = new MyThread();
        MyThread t5 = new MyThread();

        //给线程设置名字
        t1.setName("小A");
        t2.setName("小QQ");
        t3.setName("小哈哈");
        t4.setName("小诗诗");
        t5.setName("小丹丹");

        //启动线程
        t1.start();
        t2.start();
        t3.start();
        t4.start();
        t5.start();
    }
}
```

解决方案二：

```java
public class MyThread extends Thread{

    //总金额
    static BigDecimal money = BigDecimal.valueOf(100.0);
    //个数
    static int count = 3;
    //最小抽奖金额
    static final BigDecimal MIN = BigDecimal.valueOf(0.01);

    @Override
    public void run() {
        synchronized (MyThread.class){
            if(count == 0){
                System.out.println(getName() + "没有抢到红包！");
            }else{
                //中奖金额
                BigDecimal prize;
                if(count == 1){
                    prize = money;
                }else{
                    //获取抽奖范围
                    double bounds = money.subtract(BigDecimal.valueOf(count-1).multiply(MIN)).doubleValue();
                    Random r = new Random();
                    //抽奖金额
                    prize = BigDecimal.valueOf(r.nextDouble(bounds));
                }
                //设置抽中红包，小数点保留两位，四舍五入
                prize = prize.setScale(2,RoundingMode.HALF_UP);
                //在总金额中去掉对应的钱
                money = money.subtract(prize);
                //红包少了一个
                count--;
                //输出红包信息
                System.out.println(getName() + "抽中了" + prize + "元");
            }
        }
    }
}

public class Test {
    public static void main(String[] args) {
        /*
            微信中的抢红包也用到了多线程。
            假设：100块，分成了3个包，现在有5个人去抢。
            其中，红包是共享数据。
            5个人是5条线程。
            打印结果如下：
            	XXX抢到了XXX元
            	XXX抢到了XXX元
            	XXX抢到了XXX元
            	XXX没抢到
            	XXX没抢到
        */


        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();
        MyThread t3 = new MyThread();
        MyThread t4 = new MyThread();
        MyThread t5 = new MyThread();

        t1.setName("小A");
        t2.setName("小QQ");
        t3.setName("小哈哈");
        t4.setName("小诗诗");
        t5.setName("小丹丹");

        t1.start();
        t2.start();
        t3.start();
        t4.start();
        t5.start();
    }
}
```

### 练习五：抽奖箱

需求：

​	有一个抽奖池,该抽奖池中存放了奖励的金额,该抽奖池中的奖项为 {10,5,20,50,100,200,500,800,2,80,300,700}; 

创建两个抽奖箱(线程)设置线程名称分别为“抽奖箱1”，“抽奖箱2” 

随机从抽奖池中获取奖项元素并打印在控制台上,格式如下:

​               每次抽出一个奖项就打印一个(随机)

​		抽奖箱1 又产生了一个 10 元大奖

  		抽奖箱1 又产生了一个 100 元大奖
  	
  		抽奖箱1 又产生了一个 200 元大奖
  	
  		抽奖箱1 又产生了一个 800 元大奖  

​		抽奖箱2 又产生了一个 700 元大奖  

 		 .....

```java
public class MyThread extends Thread {

    ArrayList<Integer> list;

    public MyThread(ArrayList<Integer> list) {
        this.list = list;
    }

    @Override
    public void run() {
        //1.循环
        //2.同步代码块
        //3.判断
        //4.判断

        while (true) {
            synchronized (MyThread.class) {
                if (list.size() == 0) {
                    break;
                } else {
                    //继续抽奖
                    Collections.shuffle(list);
                    int prize = list.remove(0);
                    System.out.println(getName() + "又产生了一个" + prize + "元大奖");
                }
            }
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }

        }
    }
}



public class Test {
    public static void main(String[] args) {
        /*
            有一个抽奖池,该抽奖池中存放了奖励的金额,该抽奖池中的奖项为 {10,5,20,50,100,200,500,800,2,80,300,700};
            创建两个抽奖箱(线程)设置线程名称分别为“抽奖箱1”，“抽奖箱2”
            随机从抽奖池中获取奖项元素并打印在控制台上,格式如下:
                             每次抽出一个奖项就打印一个(随机)
            	抽奖箱1 又产生了一个 10 元大奖
            	抽奖箱1 又产生了一个 100 元大奖
            	抽奖箱1 又产生了一个 200 元大奖
            	抽奖箱1 又产生了一个 800 元大奖
            	抽奖箱2 又产生了一个 700 元大奖
            	.....
        */

        //创建奖池
        ArrayList<Integer> list = new ArrayList<>();
        Collections.addAll(list,10,5,20,50,100,200,500,800,2,80,300,700);

        //创建线程
        MyThread t1 = new MyThread(list);
        MyThread t2 = new MyThread(list);

        //设置名字
        t1.setName("抽奖箱1");
        t2.setName("抽奖箱2");

        //启动线程
        t1.start();
        t2.start();
    }
}
```



### 练习六：多线程统计并求最大值

需求：

​	在上一题基础上继续完成如下需求：

​     每次抽的过程中，不打印，抽完时一次性打印(随机)

​     在此次抽奖过程中，抽奖箱1总共产生了6个奖项。

​              分别为：10,20,100,500,2,300最高奖项为300元，总计额为932元

​     在此次抽奖过程中，抽奖箱2总共产生了6个奖项。

​              分别为：5,50,200,800,80,700最高奖项为800元，总计额为1835元

解决方案一：

```java
public class MyThread extends Thread {

    ArrayList<Integer> list;

    public MyThread(ArrayList<Integer> list) {
        this.list = list;
    }

    //线程一
    static ArrayList<Integer> list1 = new ArrayList<>();
    //线程二
    static ArrayList<Integer> list2 = new ArrayList<>();

    @Override
    public void run() {
        while (true) {
            synchronized (MyThread.class) {
                if (list.size() == 0) {
                    if("抽奖箱1".equals(getName())){
                        System.out.println("抽奖箱1" + list1);
                    }else {
                        System.out.println("抽奖箱2" + list2);
                    }
                    break;
                } else {
                    //继续抽奖
                    Collections.shuffle(list);
                    int prize = list.remove(0);
                    if("抽奖箱1".equals(getName())){
                        list1.add(prize);
                    }else {
                        list2.add(prize);
                    }
                }
            }
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }

        }
    }
}

public class Test {
    public static void main(String[] args) {
        /*
            有一个抽奖池,该抽奖池中存放了奖励的金额,该抽奖池中的奖项为 {10,5,20,50,100,200,500,800,2,80,300,700};
            创建两个抽奖箱(线程)设置线程名称分别为“抽奖箱1”，“抽奖箱2”
            随机从抽奖池中获取奖项元素并打印在控制台上,格式如下:
            每次抽的过程中，不打印，抽完时一次性打印(随机)    在此次抽奖过程中，抽奖箱1总共产生了6个奖项。
                分别为：10,20,100,500,2,300最高奖项为300元，总计额为932元
            在此次抽奖过程中，抽奖箱2总共产生了6个奖项。
                分别为：5,50,200,800,80,700最高奖项为800元，总计额为1835元
        */

        //创建奖池
        ArrayList<Integer> list = new ArrayList<>();
        Collections.addAll(list,10,5,20,50,100,200,500,800,2,80,300,700);

        //创建线程
        MyThread t1 = new MyThread(list);
        MyThread t2 = new MyThread(list);

        //设置名字
        t1.setName("抽奖箱1");
        t2.setName("抽奖箱2");

        //启动线程
        t1.start();
        t2.start();
    }
}

```

解决方案二：

```java
public class MyThread extends Thread {

    ArrayList<Integer> list;

    public MyThread(ArrayList<Integer> list) {
        this.list = list;
    }

    @Override
    public void run() {
        ArrayList<Integer> boxList = new ArrayList<>();//1 //2
        while (true) {
            synchronized (MyThread.class) {
                if (list.size() == 0) {
                    System.out.println(getName() + boxList);
                    break;
                } else {
                    //继续抽奖
                    Collections.shuffle(list);
                    int prize = list.remove(0);
                    boxList.add(prize);
                }
            }
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }

        }
    }
}

public class Test {
    public static void main(String[] args) {
        /*
            有一个抽奖池,该抽奖池中存放了奖励的金额,该抽奖池中的奖项为 {10,5,20,50,100,200,500,800,2,80,300,700};
            创建两个抽奖箱(线程)设置线程名称分别为“抽奖箱1”，“抽奖箱2”
            随机从抽奖池中获取奖项元素并打印在控制台上,格式如下:
            每次抽的过程中，不打印，抽完时一次性打印(随机)    在此次抽奖过程中，抽奖箱1总共产生了6个奖项。
                分别为：10,20,100,500,2,300最高奖项为300元，总计额为932元
            在此次抽奖过程中，抽奖箱2总共产生了6个奖项。
                分别为：5,50,200,800,80,700最高奖项为800元，总计额为1835元
        */

        //创建奖池
        ArrayList<Integer> list = new ArrayList<>();
        Collections.addAll(list,10,5,20,50,100,200,500,800,2,80,300,700);

        //创建线程
        MyThread t1 = new MyThread(list);
        MyThread t2 = new MyThread(list);


        //设置名字
        t1.setName("抽奖箱1");
        t2.setName("抽奖箱2");


        //启动线程
        t1.start();
        t2.start();

    }
}
```



### 练习七：多线程之间的比较 

需求：

​	在上一题基础上继续完成如下需求：

​	在此次抽奖过程中，抽奖箱1总共产生了6个奖项，分别为：10,20,100,500,2,300

  	最高奖项为300元，总计额为932元

​	在此次抽奖过程中，抽奖箱2总共产生了6个奖项，分别为：5,50,200,800,80,700

  	最高奖项为800元，总计额为1835元

​	在此次抽奖过程中,抽奖箱2中产生了最大奖项,该奖项金额为800元

​	以上打印效果只是数据模拟,实际代码运行的效果会有差异

```java
public class MyCallable implements Callable<Integer> {

    ArrayList<Integer> list;

    public MyCallable(ArrayList<Integer> list) {
        this.list = list;
    }

    @Override
    public Integer call() throws Exception {
        ArrayList<Integer> boxList = new ArrayList<>();//1 //2
        while (true) {
            synchronized (MyCallable.class) {
                if (list.size() == 0) {
                    System.out.println(Thread.currentThread().getName() + boxList);
                    break;
                } else {
                    //继续抽奖
                    Collections.shuffle(list);
                    int prize = list.remove(0);
                    boxList.add(prize);
                }
            }
            Thread.sleep(10);
        }
        //把集合中的最大值返回
        if(boxList.size() == 0){
            return null;
        }else{
            return Collections.max(boxList);
        }
    }
}

package com.itheima.test7;

import java.util.ArrayList;
import java.util.Collections;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.FutureTask;

public class Test {
    public static void main(String[] args) throws ExecutionException, InterruptedException {
        /*
            有一个抽奖池,该抽奖池中存放了奖励的金额,该抽奖池中的奖项为 {10,5,20,50,100,200,500,800,2,80,300,700};
            创建两个抽奖箱(线程)设置线程名称分别为    "抽奖箱1", "抽奖箱2"
            随机从抽奖池中获取奖项元素并打印在控制台上,格式如下:

            在此次抽奖过程中，抽奖箱1总共产生了6个奖项，分别为：10,20,100,500,2,300
        	    最高奖项为300元，总计额为932元

            在此次抽奖过程中，抽奖箱2总共产生了6个奖项，分别为：5,50,200,800,80,700
            	最高奖项为800元，总计额为1835元

            在此次抽奖过程中,抽奖箱2中产生了最大奖项,该奖项金额为800元
            核心逻辑：获取线程抽奖的最大值（看成是线程运行的结果）


            以上打印效果只是数据模拟,实际代码运行的效果会有差异
        */

        //创建奖池
        ArrayList<Integer> list = new ArrayList<>();
        Collections.addAll(list,10,5,20,50,100,200,500,800,2,80,300,700);

        //创建多线程要运行的参数对象
        MyCallable mc = new MyCallable(list);

        //创建多线程运行结果的管理者对象
        //线程一
        FutureTask<Integer> ft1 = new FutureTask<>(mc);
        //线程二
        FutureTask<Integer> ft2 = new FutureTask<>(mc);

        //创建线程对象
        Thread t1 = new Thread(ft1);
        Thread t2 = new Thread(ft2);

        //设置名字
        t1.setName("抽奖箱1");
        t2.setName("抽奖箱2");

        //开启线程
        t1.start();
        t2.start();


        Integer max1 = ft1.get();
        Integer max2 = ft2.get();

        System.out.println(max1);
        System.out.println(max2);

        //在此次抽奖过程中,抽奖箱2中产生了最大奖项,该奖项金额为800元
        if(max1 == null){
            System.out.println("在此次抽奖过程中,抽奖箱2中产生了最大奖项,该奖项金额为"+max2+"元");
        }else if(max2 == null){
            System.out.println("在此次抽奖过程中,抽奖箱1中产生了最大奖项,该奖项金额为"+max1+"元");
        }else if(max1 > max2){
            System.out.println("在此次抽奖过程中,抽奖箱1中产生了最大奖项,该奖项金额为"+max1+"元");
        }else if(max1 < max2){
            System.out.println("在此次抽奖过程中,抽奖箱2中产生了最大奖项,该奖项金额为"+max2+"元");
        }else{
            System.out.println("两者的最大奖项是一样的");
        }
    }
}
```







## 2. 原子性

### 2.1 volatile-问题

**代码分析 :** 

```java
package com.itheima.myvolatile;

public class Demo {
    public static void main(String[] args) {
        MyThread1 t1 = new MyThread1();
        t1.setName("小路同学");
        t1.start();

        MyThread2 t2 = new MyThread2();
        t2.setName("小皮同学");
        t2.start();
    }
}
```

```java
package com.itheima.myvolatile;

public class Money {
    public static int money = 100000;
}
```

```java
package com.itheima.myvolatile;

public class MyThread1 extends  Thread {
    @Override
    public void run() {
        while(Money.money == 100000){

        }

        System.out.println("结婚基金已经不是十万了");
    }
}

```

```java
package com.itheima.myvolatile;

public class MyThread2 extends Thread {
    @Override
    public void run() {
        try {
            Thread.sleep(10);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        Money.money = 90000;
    }
}

```

**程序问题 :**  女孩虽然知道结婚基金是十万，但是当基金的余额发生变化的时候，女孩无法知道最新的余额。



### 2.2 volatile解决

**以上案例出现的问题 :**

​	当A线程修改了共享数据时，B线程没有及时获取到最新的值，如果还在使用原先的值，就会出现问题 

​	1，堆内存是唯一的，每一个线程都有自己的线程栈。

​	2 ，每一个线程在使用堆里面变量的时候，都会先拷贝一份到变量的副本中。

​	3 ，在线程中，每一次使用是从变量的副本中获取的。

**Volatile关键字 :** 强制线程每次在使用的时候，都会看一下共享区域最新的值

**代码实现 :** **使用volatile关键字解决**

```java
package com.itheima.myvolatile;

public class Demo {
    public static void main(String[] args) {
        MyThread1 t1 = new MyThread1();
        t1.setName("小路同学");
        t1.start();

        MyThread2 t2 = new MyThread2();
        t2.setName("小皮同学");
        t2.start();
    }
}
```

```java
package com.itheima.myvolatile;

public class Money {
    public static volatile int money = 100000;
}
```

```java
package com.itheima.myvolatile;

public class MyThread1 extends  Thread {
    @Override
    public void run() {
        while(Money.money == 100000){

        }

        System.out.println("结婚基金已经不是十万了");
    }
}

```

```java
package com.itheima.myvolatile;

public class MyThread2 extends Thread {
    @Override
    public void run() {
        try {
            Thread.sleep(10);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        Money.money = 90000;
    }
}

```



### 2.3 synchronized解决

**synchronized解决 :** 

​	1 ，线程获得锁

​	2 ，清空变量副本

​	3 ，拷贝共享变量最新的值到变量副本中

​	4 ，执行代码

​	5 ，将修改后变量副本中的值赋值给共享数据

​	6 ，释放锁

**代码实现 :** 

```java
package com.itheima.myvolatile2;

public class Demo {
    public static void main(String[] args) {
        MyThread1 t1 = new MyThread1();
        t1.setName("小路同学");
        t1.start();

        MyThread2 t2 = new MyThread2();
        t2.setName("小皮同学");
        t2.start();
    }
}
```

```java
package com.itheima.myvolatile2;

public class Money {
    public static Object lock = new Object();
    public static volatile int money = 100000;
}
```

```java
package com.itheima.myvolatile2;

public class MyThread1 extends  Thread {
    @Override
    public void run() {
        while(true){
            synchronized (Money.lock){
                if(Money.money != 100000){
                    System.out.println("结婚基金已经不是十万了");
                    break;
                }
            }
        }
    }
}
```

```java
package com.itheima.myvolatile2;

public class MyThread2 extends Thread {
    @Override
    public void run() {
        synchronized (Money.lock) {
            try {
                Thread.sleep(10);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }

            Money.money = 90000;
        }
    }
}
```



### 2.4 原子性

**概述 :** 所谓的原子性是指在一次操作或者多次操作中，要么所有的操作全部都得到了执行并且不会受到任何因素的干扰而中断，要么所有的操作都不执行，多个操作是一个不可以分割的整体。

**代码实现 :** 

```java
package com.itheima.threadatom;

public class AtomDemo {
    public static void main(String[] args) {
        MyAtomThread atom = new MyAtomThread();

        for (int i = 0; i < 100; i++) {
            new Thread(atom).start();
        }
    }
}
class MyAtomThread implements Runnable {
    private volatile int count = 0; //送冰淇淋的数量

    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            //1,从共享数据中读取数据到本线程栈中.
            //2,修改本线程栈中变量副本的值
            //3,会把本线程栈中变量副本的值赋值给共享数据.
            count++;
            System.out.println("已经送了" + count + "个冰淇淋");
        }
    }
}
```

**代码总结 :** count++ 不是一个原子性操作, 他在执行的过程中,有可能被其他线程打断



### 2.5 volatile关键字不能保证原子性

解决方案 : 我们可以给count++操作添加锁，那么count++操作就是临界区中的代码，临界区中的代码一次只能被一个线程去执行，所以count++就变成了原子操作。

```java
package com.itheima.threadatom2;

public class AtomDemo {
    public static void main(String[] args) {
        MyAtomThread atom = new MyAtomThread();

        for (int i = 0; i < 100; i++) {
            new Thread(atom).start();
        }
    }
}
class MyAtomThread implements Runnable {
    private volatile int count = 0; //送冰淇淋的数量
    private Object lock = new Object();

    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            //1,从共享数据中读取数据到本线程栈中.
            //2,修改本线程栈中变量副本的值
            //3,会把本线程栈中变量副本的值赋值给共享数据.
            synchronized (lock) {
                count++;
                System.out.println("已经送了" + count + "个冰淇淋");
            }
        }
    }
}
```



### 2.6 原子性_AtomicInteger

概述：java从JDK1.5开始提供了java.util.concurrent.atomic包(简称Atomic包)，这个包中的原子操作类提供了一种用法简单，性能高效，线程安全地更新一个变量的方式。因为变

量的类型有很多种，所以在Atomic包里一共提供了13个类，属于4种类型的原子更新方式，分别是原子更新基本类型、原子更新数组、原子更新引用和原子更新属性(字段)。本次我们只讲解

使用原子的方式更新基本类型，使用原子的方式更新基本类型Atomic包提供了以下3个类：

AtomicBoolean： 原子更新布尔类型

AtomicInteger：   原子更新整型

AtomicLong：	原子更新长整型

以上3个类提供的方法几乎一模一样，所以本节仅以AtomicInteger为例进行讲解，AtomicInteger的常用方法如下：

```java
public AtomicInteger()：	   			    初始化一个默认值为0的原子型Integer
public AtomicInteger(int initialValue)：  初始化一个指定值的原子型Integer

int get():   			 				获取值
int getAndIncrement():      			 以原子方式将当前值加1，注意，这里返回的是自增前的值。
int incrementAndGet():     				 以原子方式将当前值加1，注意，这里返回的是自增后的值。
int addAndGet(int data):				 以原子方式将输入的数值与实例中的值（AtomicInteger里的value）相加，并返回结果。
int getAndSet(int value):   			 以原子方式设置为newValue的值，并返回旧值。
```

**代码实现 :**

```java
package com.itheima.threadatom3;

import java.util.concurrent.atomic.AtomicInteger;

public class MyAtomIntergerDemo1 {
//    public AtomicInteger()：	               初始化一个默认值为0的原子型Integer
//    public AtomicInteger(int initialValue)： 初始化一个指定值的原子型Integer
    public static void main(String[] args) {
        AtomicInteger ac = new AtomicInteger();
        System.out.println(ac);

        AtomicInteger ac2 = new AtomicInteger(10);
        System.out.println(ac2);
    }

}
```

```java
package com.itheima.threadatom3;

import java.lang.reflect.Field;
import java.util.concurrent.atomic.AtomicInteger;

public class MyAtomIntergerDemo2 {
//    int get():   		 		获取值
//    int getAndIncrement():     以原子方式将当前值加1，注意，这里返回的是自增前的值。
//    int incrementAndGet():     以原子方式将当前值加1，注意，这里返回的是自增后的值。
//    int addAndGet(int data):	 以原子方式将参数与对象中的值相加，并返回结果。
//    int getAndSet(int value):  以原子方式设置为newValue的值，并返回旧值。
    public static void main(String[] args) {
//        AtomicInteger ac1 = new AtomicInteger(10);
//        System.out.println(ac1.get());

//        AtomicInteger ac2 = new AtomicInteger(10);
//        int andIncrement = ac2.getAndIncrement();
//        System.out.println(andIncrement);
//        System.out.println(ac2.get());

//        AtomicInteger ac3 = new AtomicInteger(10);
//        int i = ac3.incrementAndGet();
//        System.out.println(i);//自增后的值
//        System.out.println(ac3.get());

//        AtomicInteger ac4 = new AtomicInteger(10);
//        int i = ac4.addAndGet(20);
//        System.out.println(i);
//        System.out.println(ac4.get());

        AtomicInteger ac5 = new AtomicInteger(100);
        int andSet = ac5.getAndSet(20);
        System.out.println(andSet);
        System.out.println(ac5.get());
    }
}
```



### 2.7 AtomicInteger-内存解析

**AtomicInteger原理 :** 自旋锁  + CAS 算法

**CAS算法：**

​	有3个操作数（内存值V， 旧的预期值A，要修改的值B）

​	当旧的预期值A == 内存值   此时修改成功，将V改为B                 

​	当旧的预期值A！=内存值   此时修改失败，不做任何操作                 

​	并重新获取现在的最新值（这个重新获取的动作就是自旋）

### 2.8 AtomicInteger-源码解析

**代码实现 :**

```java
package com.itheima.threadatom4;

public class AtomDemo {
    public static void main(String[] args) {
        MyAtomThread atom = new MyAtomThread();

        for (int i = 0; i < 100; i++) {
            new Thread(atom).start();
        }
    }
}
```

```java
package com.itheima.threadatom4;

import java.util.concurrent.atomic.AtomicInteger;

public class MyAtomThread implements Runnable {
    //private volatile int count = 0; //送冰淇淋的数量
    //private Object lock = new Object();
    AtomicInteger ac = new AtomicInteger(0);

    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            //1,从共享数据中读取数据到本线程栈中.
            //2,修改本线程栈中变量副本的值
            //3,会把本线程栈中变量副本的值赋值给共享数据.
            //synchronized (lock) {
//                count++;
//                ac++;
            int count = ac.incrementAndGet();
            System.out.println("已经送了" + count + "个冰淇淋");
           // }
        }
    }
}

```

**源码解析 :** 

```java
//先自增，然后获取自增后的结果
public final int incrementAndGet() {
        //+ 1 自增后的结果
        //this 就表示当前的atomicInteger（值）
        //1    自增一次
        return U.getAndAddInt(this, VALUE, 1) + 1;
}

public final int getAndAddInt(Object o, long offset, int delta) {
        //v 旧值
        int v;
        //自旋的过程
        do {
            //不断的获取旧值
            v = getIntVolatile(o, offset);
            //如果这个方法的返回值为false，那么继续自旋
            //如果这个方法的返回值为true，那么自旋结束
            //o 表示的就是内存值
            //v 旧值
            //v + delta 修改后的值
        } while (!weakCompareAndSetInt(o, offset, v, v + delta));
            //作用：比较内存中的值，旧值是否相等，如果相等就把修改后的值写到内存中，返回true。表示修改成功。
            //                                 如果不相等，无法把修改后的值写到内存中，返回false。表示修改失败。
            //如果修改失败，那么继续自旋。
        return v;
}
```



### 2.9 悲观锁和乐观锁

**synchronized和CAS的区别 :** 

**相同点：**在多线程情况下，都可以保证共享数据的安全性。

**不同点：**synchronized总是从最坏的角度出发，认为每次获取数据的时候，别人都有可能修改。所以在每                       次操作共享数据之前，都会上锁。（悲观锁）

​	cas是从乐观的角度出发，假设每次获取数据别人都不会修改，所以不会上锁。只不过在修改共享数据的时候，会检查一下，别人有没有修改过这个数据。

​	如果别人修改过，那么我再次获取现在最新的值。            

​	 如果别人没有修改过，那么我现在直接修改共享数据的值.(乐观锁）



## 3. 并发工具类

### 3.1 并发工具类-Hashtable

​	**Hashtable出现的原因 :** 在集合类中HashMap是比较常用的集合对象，但是HashMap是线程不安全的(多线程环境下可能会存在问题)。为了保证数据的安全性我们可以使用Hashtable，但是Hashtable的效率低下。

**代码实现 :** 

```java
package com.itheima.mymap;

import java.util.HashMap;
import java.util.Hashtable;

public class MyHashtableDemo {
    public static void main(String[] args) throws InterruptedException {
        Hashtable<String, String> hm = new Hashtable<>();

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 25; i++) {
                hm.put(i + "", i + "");
            }
        });


        Thread t2 = new Thread(() -> {
            for (int i = 25; i < 51; i++) {
                hm.put(i + "", i + "");
            }
        });

        t1.start();
        t2.start();

        System.out.println("----------------------------");
        //为了t1和t2能把数据全部添加完毕
        Thread.sleep(1000);

        //0-0 1-1 ..... 50- 50

        for (int i = 0; i < 51; i++) {
            System.out.println(hm.get(i + ""));
        }//0 1 2 3 .... 50


    }
}
```



### 3.2 并发工具类-ConcurrentHashMap基本使用

​	**ConcurrentHashMap出现的原因 :** 在集合类中HashMap是比较常用的集合对象，但是HashMap是线程不安全的(多线程环境下可能会存在问题)。为了保证数据的安全性我们可以使用Hashtable，但是Hashtable的效率低下。

基于以上两个原因我们可以使用JDK1.5以后所提供的ConcurrentHashMap。

**体系结构 :** 

![1591168965857](C:\Users\周歆怡\Desktop\资料\day32-多线程&juc\笔记\img\1591168965857.png)

**总结 :** 

​	1 ，HashMap是线程不安全的。多线程环境下会有数据安全问题

​	2 ，Hashtable是线程安全的，但是会将整张表锁起来，效率低下

​	3，ConcurrentHashMap也是线程安全的，效率较高。     在JDK7和JDK8中，底层原理不一样。

**代码实现 :** 

```java
package com.itheima.mymap;

import java.util.Hashtable;
import java.util.concurrent.ConcurrentHashMap;

public class MyConcurrentHashMapDemo {
    public static void main(String[] args) throws InterruptedException {
        ConcurrentHashMap<String, String> hm = new ConcurrentHashMap<>(100);

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 25; i++) {
                hm.put(i + "", i + "");
            }
        });


        Thread t2 = new Thread(() -> {
            for (int i = 25; i < 51; i++) {
                hm.put(i + "", i + "");
            }
        });

        t1.start();
        t2.start();

        System.out.println("----------------------------");
        //为了t1和t2能把数据全部添加完毕
        Thread.sleep(1000);

        //0-0 1-1 ..... 50- 50

        for (int i = 0; i < 51; i++) {
            System.out.println(hm.get(i + ""));
        }//0 1 2 3 .... 50
    }
}
```



### 3.3 并发工具类-ConcurrentHashMap1.7原理

![1591169254280](C:\Users\周歆怡\Desktop\资料\day32-多线程&juc\笔记\img\1591169254280.png)

### 3.4 并发工具类-ConcurrentHashMap1.8原理

![1591169338256](C:\Users\周歆怡\Desktop\资料\day32-多线程&juc\笔记\img\1591169338256.png)

**总结 :** 

​	1，如果使用空参构造创建ConcurrentHashMap对象，则什么事情都不做。     在第一次添加元素的时候创建哈希表

​	2，计算当前元素应存入的索引。

​	3，如果该索引位置为null，则利用cas算法，将本结点添加到数组中。

​	4，如果该索引位置不为null，则利用volatile关键字获得当前位置最新的结点地址，挂在他下面，变成链表。		

​	5，当链表的长度大于等于8时，自动转换成红黑树6，以链表或者红黑树头结点为锁对象，配合悲观锁保证多线程操作集合时数据的安全性

### 3.5 并发工具类-CountDownLatch

**CountDownLatch类 :** 		

| 方法                             | 解释                             |
| -------------------------------- | -------------------------------- |
| public CountDownLatch(int count) | 参数传递线程数，表示等待线程数量 |
| public void await()              | 让线程等待                       |
| public void countDown()          | 当前线程执行完毕                 |

**使用场景：** 让某一条线程等待其他线程执行完毕之后再执行

**代码实现 :** 

```java
package com.itheima.mycountdownlatch;

import java.util.concurrent.CountDownLatch;

public class ChileThread1 extends Thread {

    private CountDownLatch countDownLatch;
    public ChileThread1(CountDownLatch countDownLatch) {
        this.countDownLatch = countDownLatch;
    }

    @Override
    public void run() {
        //1.吃饺子
        for (int i = 1; i <= 10; i++) {
            System.out.println(getName() + "在吃第" + i + "个饺子");
        }
        //2.吃完说一声
        //每一次countDown方法的时候，就让计数器-1
        countDownLatch.countDown();
    }
}

```

```java
package com.itheima.mycountdownlatch;

import java.util.concurrent.CountDownLatch;

public class ChileThread2 extends Thread {

    private CountDownLatch countDownLatch;
    public ChileThread2(CountDownLatch countDownLatch) {
        this.countDownLatch = countDownLatch;
    }
    @Override
    public void run() {
        //1.吃饺子
        for (int i = 1; i <= 15; i++) {
            System.out.println(getName() + "在吃第" + i + "个饺子");
        }
        //2.吃完说一声
        //每一次countDown方法的时候，就让计数器-1
        countDownLatch.countDown();
    }
}

```

```java
package com.itheima.mycountdownlatch;

import java.util.concurrent.CountDownLatch;

public class ChileThread3 extends Thread {

    private CountDownLatch countDownLatch;
    public ChileThread3(CountDownLatch countDownLatch) {
        this.countDownLatch = countDownLatch;
    }
    @Override
    public void run() {
        //1.吃饺子
        for (int i = 1; i <= 20; i++) {
            System.out.println(getName() + "在吃第" + i + "个饺子");
        }
        //2.吃完说一声
        //每一次countDown方法的时候，就让计数器-1
        countDownLatch.countDown();
    }
}

```

```java
package com.itheima.mycountdownlatch;

import java.util.concurrent.CountDownLatch;

public class MotherThread extends Thread {
    private CountDownLatch countDownLatch;
    public MotherThread(CountDownLatch countDownLatch) {
        this.countDownLatch = countDownLatch;
    }

    @Override
    public void run() {
        //1.等待
        try {
            //当计数器变成0的时候，会自动唤醒这里等待的线程。
            countDownLatch.await();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        //2.收拾碗筷
        System.out.println("妈妈在收拾碗筷");
    }
}

```

```java
package com.itheima.mycountdownlatch;

import java.util.concurrent.CountDownLatch;

public class MyCountDownLatchDemo {
    public static void main(String[] args) {
        //1.创建CountDownLatch的对象，需要传递给四个线程。
        //在底层就定义了一个计数器，此时计数器的值就是3
        CountDownLatch countDownLatch = new CountDownLatch(3);
        //2.创建四个线程对象并开启他们。
        MotherThread motherThread = new MotherThread(countDownLatch);
        motherThread.start();

        ChileThread1 t1 = new ChileThread1(countDownLatch);
        t1.setName("小明");

        ChileThread2 t2 = new ChileThread2(countDownLatch);
        t2.setName("小红");

        ChileThread3 t3 = new ChileThread3(countDownLatch);
        t3.setName("小刚");

        t1.start();
        t2.start();
        t3.start();
    }
}
```

**总结 :** 

​	1. CountDownLatch(int count)：参数写等待线程的数量。并定义了一个计数器。

​	2. await()：让线程等待，当计数器为0时，会唤醒等待的线程

​	3. countDown()： 线程执行完毕时调用，会将计数器-1。

### 3.6 并发工具类-Semaphore

**使用场景 :** 

​	可以控制访问特定资源的线程数量。

**实现步骤 :** 

​	1，需要有人管理这个通道

​	2，当有车进来了，发通行许可证

​	3，当车出去了，收回通行许可证

​	4，如果通行许可证发完了，那么其他车辆只能等着

**代码实现 :** 

```java
package com.itheima.mysemaphore;

import java.util.concurrent.Semaphore;

public class MyRunnable implements Runnable {
    //1.获得管理员对象，
    private Semaphore semaphore = new Semaphore(2);
    @Override
    public void run() {
        //2.获得通行证
        try {
            semaphore.acquire();
            //3.开始行驶
            System.out.println("获得了通行证开始行驶");
            Thread.sleep(2000);
            System.out.println("归还通行证");
            //4.归还通行证
            semaphore.release();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}

```

```java
package com.itheima.mysemaphore;

public class MySemaphoreDemo {
    public static void main(String[] args) {
        MyRunnable mr = new MyRunnable();

        for (int i = 0; i < 100; i++) {
            new Thread(mr).start();
        }
    }
}
```





# 网络编程

## 1 网络编程概述

<font color=blue>**1. 什么是网络编程？**</font>

**计算机网络**：将地理位置不同的、具有独立功能的多台计算机及其外部设备，通过通信线路连接起来，在网络操作系统，网络管理软件及网络通信协议的管理和协调下，实现资源共享和信息传递的计算机系统

**网络编程**：在网络通信协议下，不同计算机上运行的程序，可以进行数据传输

- Java中可使用<font color=red>**java.net**</font>包下的技术开发出常见的网络应用程序

<font color=blue>**2. 常见的软件架构有什么？**</font>

- **C/S**：Client/Server 客户端/服务器
  - 在**用户本地需要下载并安装客户端程序**，在远程有一个服务器端程序
  - 优点：
    - 画面可以做的非常精美，用户体验好
    - 需要开发客户端，也需要开发服务端
  - 缺点：
    - 用户需要下载和更新的时候太麻烦
  - 适合定制专业化的办公类软件，如IDEA、网游
- **B/S**：Browser/Server 浏览器/服务器
  - **只需要一个浏览器**，用户通过不同网站，客户访问不同的服务器
  - 优点：
    - 不需要开发客户端，只需要页面+服务端
    - 用户不需要下载，打开浏览器就能使用
  - 缺点：
    - 如果应用过大，用户体验受到影响
  - 适合移动互联网应用，可以在任何地方随时访问的系统

<font color=blue>**3. 网络编程三要素是什么？**</font>

- **IP地址**

  - <font color=red>**设备在网络中的地址**</font>，是唯一的标识


  要想让网络中的计算机能够互相通信，必须为每台计算机指定一个标识号，通过这个标识号来指定要接收数据的计算机和识别发送的计算机，而IP地址就是这个标识号。也就是设备的标识

- **端口**

  - <font color=red>**应用程序在设备中**</font>唯一的标识


  网络的通信，本质上是两个应用程序的通信。每台计算机都有很多的应用程序，那么在网络通信时，如何区分这些应用程序呢？如果说IP地址可以唯一标识网络中的设备，那么端口号就可以唯一标识设备中的应用程序了。也就是应用程序的标识

- **协议**

  - <font color=red>**数据在网络中传输的规则**</font>，常见的协议有UDP、TCP、http、https、ftp

  通过计算机网络可以使多台计算机实现连接，位于同一个网络中的计算机在进行连接和通信时需要遵守一定的规则，这就好比在道路中行驶的汽车一定要遵守交通规则一样。在计算机网络中，这些连接和通信的规则被称为网络通信协议，它对数据的传输格式、传输速率、传输步骤等做了统一规定，通信双方必须同时遵守才能完成数据交换。常见的协议有UDP协议和TCP协议

  


### 1.1 IP地址

IP地址(**Internet Protocol**)：是网络中设备的唯一标识，是分配给上网设备的数字标签

<font color=blue>**1. IP地址有哪两大类？**</font>

- **IPV4**

  - 全称：Internet Protocol version 4，互联网通信协议第四版
  - 简述：采用32位地址长度，分成四组，即给每个连接在网络上的主机分配一个<font color=red>**32bit地址**</font>
  - 例如一个采用二进制形式的IP地址是“11000000 10101000 00000001 01000010”，为了方便使用，写成十进制形式，表示为“192.168.1.66”。即采用"<font color=red>**点分十进制表示法**</font>"
  - 截至2019年11月26日全部分配完毕

- **IPV6**

  - 全称：Internet Protocol version 6，互联网通信协议第六版
  - 简述：采用<font color=red>**128位地址长度**</font>，分成八组
  - 为了扩大地址空间，通过IPv6重新定义地址空间，采用128位地址长度，每16个字节一组，分成8组十六进制数。例如一个采用二进制形式的IP地址是"00100000 00000001 00001101 10111000 00000000 00000000 00000000 00100011 00000000 00001000 00001000 00000000 00100000 00001100 01000001 01111010"，采用<font color=red>**冒分十六进制表示法**</font>，2001:0DB8:0000:0023:0008:0800:200C:417A，省略前面的0，为2001:DB8:0:23:8:800:200c:417A

  - 特殊情况：计算出的16进制表示形式中间有多个连续的0，采用<font color=red>**0位压缩表示法**</font>，为FF01::1101

<font color=blue>**2. IPV4的地址分类形式有哪些？**</font>

- 公网地址(万维网使用)、私有地址(局域网使用)
- <font color=red>**192.168.开头的是私有地址**</font>,范围为192.168.0.0--192.168.255.255，专门为组织机构内部使用，以此节省IP
- 特殊IP地址：127.0.0.1，即localhost，回送地址，可以代表本机地址，一般用来测试使用，永远只会寻找当前所在的本机

==面试题：假设192.168.1.100是我的电脑的IP，那么这个IP跟127.0.0.1是一样的吗？==

当变更场所时，局域网IP有可能会发生改变，而127.0.0.1不会变

<font color=blue>**3. DOS常用命令有哪些?**</font>

- <font color=red>**ipconfig**</font>：查看本机IP地址

- <font color=red>**ping IP地址**</font>：检查网络是否连通

  

### 1.2 InetAddress

**InetAddress**：此类表示Internet协议（IP）地址

<font color=blue>**1. 相关方法**</font>

| 方法名                                        | 说明                                                         |
| --------------------------------------------- | ------------------------------------------------------------ |
| static InetAddress **getByName(String host)** | 确定主机名称的IP地址。主机名称可以是机器名称，也可以是IP地址 |
| String **getHostName()**                      | 获取此IP地址的主机名                                         |
| String **getHostAddress()**                   | 返回文本显示中的IP地址字符串                                 |

<font color=blue>**2. 代码演示**</font>

```java
public class InetAddressDemo {
    public static void main(String[] args) throws UnknownHostException {
		//1.获取InetAddress的对象
        InetAddress address = InetAddress.getByName("192.168.1.66");
        InetAddress address2 = InetAddress.getByName("DESKTOP-");

        //2.获取此IP地址的主机名
        String name = address.getHostName();
        //3.返回文本显示中的IP地址字符串
        String ip = address.getHostAddress();

        System.out.println("主机名：" + name);
        System.out.println("IP地址：" + ip);
    }
}
```



### 1.3 端口和协议

<font color=blue>**1. 端口号**</font>

- **端口**：设备上应用程序的唯一标识

- **端口号**：由两个字节表示的整数，取值范围为0-65535，其中0-1023之间的端口号用于一些知名的网络服务/应用，<font color=red>**一个端口号只能被一个应用程序使用**</font>，如果端口号被另外一个服务或应用所占用，会导致当前程序启动失败

<font color=blue>**2. 协议**</font>

- **协议**：计算机网络中，连接和通信的规则被称为网络通信协议

  - **OSI参考模型**：世界互联协议标准，全球通信规范，单模型过于理想化，未能在因特网上进行广泛推广

  - **TCP/IP参考模型**：事实上的国际标准

    | OSI参考模型            | TCP/IP参考模型   | TCP/IP参考模型各层对应协议 | 面向哪些                                                 |
    | ---------------------- | ---------------- | -------------------------- | -------------------------------------------------------- |
    | 应用层、表示层、会话层 | 应用层           | HTTP、FTP、Telnet、DNS...  | 应用程序关注的，如浏览器、邮箱等，程序员一般在这一层开发 |
    | 传输层                 | 传输层           | TCP、UDP...                | 选择传输使用的TCP、UDP协议                               |
    | 网络层                 | 网络层           | IP、ICMP、ARP...           | 封装自己的IP，对方的IP等信息                             |
    | 数据链路层、物理层     | 物理、数据链路层 | 硬件设备010101...          | 转换成二进制利用物理设备传输                             |

- **UDP协议**

  - <font color=red>**用户数据报协议(User Datagram Protocol)**</font>
  - UDP是<font color=red>**无连接**</font>通信协议，即在数据传输时，数据的发送端和接收端不建立逻辑连接。简单来说，当一台计算机向另外一台计算机发送数据时，发送端不会确认接收端是否存在，就会发出数据，同样接收端在收到数据时，也不会向发送端反馈是否收到数据。
  - **特点**：速度快、有大小限制一次最多发送64K，数据不安全，易丢失数据
  - **适用场合**：由于使用UDP协议消耗系统资源小，通信效率高，所以通常都会用于音频、视频和普通数据的传输。例如视频会议通常采用UDP协议，因为这种情况即使偶尔丢失一两个数据包，也不会对接收结果产生太大影响。但是在使用UDP协议传送数据时，由于UDP的面向无连接性，不能保证数据的完整性，因此在**传输重要数据时不建议使用UDP协议**

- **TCP协议**

  - <font color=red>**传输控制协议 (Transmission Control Protocol)**</font>

  - TCP协议是<font color=red>**面向连接**</font>的通信协议，即传输数据之前，在发送端和接收端建立逻辑连接，然后再传输数据，它提供了两台计算机之间可靠无差错的数据传输。在TCP连接中必须要明确客户端与服务器端，由客户端向服务端发出连接请求，每次连接的创建都需要经过“三次握手”

  - **特点**：速度慢、没有大小限制、数据安全

  - **三次握手**：TCP协议中，在发送数据的准备阶段，客户端与服务器之间的三次交互，以保证连接的可靠

    第一次握手，客户端向服务器端发出连接请求，等待服务器确认

    第二次握手，服务器端向客户端回送一个响应，通知客户端收到了连接请求

    第三次握手，客户端再次向服务器端发送确认信息，确认连接

  - 完成三次握手，连接建立后，客户端和服务器就可以开始进行数据传输了。由于这种面向连接的特性，TCP协议可以保证传输数据的安全，所以应用十分广泛。例如上传文件、下载文件、浏览网页等



## 2 UDP通信程序

### 2.1 UDP基本使用

<font color=blue>**1. UDP发送数据**</font>

- **Java中的UDP通信**

  - UDP协议是一种不可靠的网络协议，它在通信的两端各建立一个Socket对象，但是这两个Socket只是发送，接收数据的对象，因此对于基于UDP协议的通信双方而言，没有所谓的客户端和服务器的概念
  - Java提供了DatagramSocket类作为基于UDP协议的Socket

- **构造方法**

  | 方法名                                                      | 说明                                                 |
  | ----------------------------------------------------------- | ---------------------------------------------------- |
  | DatagramSocket()                                            | 创建数据报套接字并将其绑定到本机地址上的任何可用端口 |
  | DatagramPacket(byte[] buf,int len,InetAddress add,int port) | 创建数据包,发送长度为len的数据包到指定主机的指定端口 |

- **相关方法**

  | 方法名                         | 说明                   |
  | ------------------------------ | ---------------------- |
  | void send(DatagramPacket p)    | 发送数据报包           |
  | void close()                   | 关闭数据报套接字       |
  | void receive(DatagramPacket p) | 从此套接字接受数据报包 |

- **发送数据的步骤**

  - 创建发送端的Socket对象(DatagramSocket)
  - 创建数据，并把数据打包
  - 调用DatagramSocket对象的方法发送数据
  - 关闭发送端

- **代码演示**

  ```java
  public class SendDemo {
      public static void main(String[] args) throws IOException {
          //1. 创建发送端的Socket对象(DatagramSocket) --- 快递公司
          //细节：绑定端口，以后可通过此端口往外发送
          //空参：所有可用的端口中随机一个进行使用
          //有参：指定端口进行绑定
          DatagramSocket ds = new DatagramSocket();
  
          //2. 创建数据，并把数据打包
          //DatagramPacket(byte[] buf, int length, InetAddress address, int port)
          //构造一个数据包，发送长度为 length的数据包到指定主机上的指定端口号。
          byte[] bys = "hello,udp,我来了".getBytes();
          InetAddress address = InetAddress.getByName("127.0.0.1");
          int port = 10086;
          DatagramPacket dp = new DatagramPacket(bys,bys.length,address,port);
  
          //3. 调用DatagramSocket对象的方法发送数据
          ds.send(dp);
  
          //4. 关闭发送端，释放资源
          ds.close();
      }
  }
  ```

<font color=blue>**2. UDP接收数据**</font>

- **接收数据的步骤**

  - 创建接收端的Socket对象(DatagramSocket)
  - 创建一个数据包，用于接收数据
  - 调用DatagramSocket对象的方法接收数据
  - 解析数据包，并把数据在控制台显示
  - 关闭接收端

- **构造方法**

  | 方法名                              | 说明                                            |
  | ----------------------------------- | ----------------------------------------------- |
  | DatagramPacket(byte[] buf, int len) | 创建一个DatagramPacket用于接收长度为len的数据包 |

- **相关方法**

  | 方法名            | 说明                                     |
  | ----------------- | ---------------------------------------- |
  | byte[]  getData() | 返回数据缓冲区                           |
  | int  getLength()  | 返回要发送的数据的长度或接收的数据的长度 |

- **示例代码**

  ```java
  public class ReceiveDemo {
      public static void main(String[] args) throws IOException {
        	//1. 创建接收端的Socket对象(DatagramSocket)
          //细节：接收时一定要绑定端口，并且绑定的端口一定要和发送的端口保持一致
        	DatagramSocket ds = new DatagramSocket(12345);
  
        	//2. 创建一个数据包，用于接收数据
        	byte[] bys = new byte[1024];
        	DatagramPacket dp = new DatagramPacket(bys, bys.length);
        	ds.receive(dp);
  
        	//3. 解析数据包，并把数据在控制台显示
          byte[] data = dp.getData();
          int len = dp.getLength();
          IntetAddress address = dp.getAddress();
          int port = dp.getPort();
        	System.out.println("数据是：" + new String(data, 0,len));
          System.out.println("该数据是从:"+address+port)；
          
          //4. 释放资源
          ds.close();    
      }
  }
  ```

<font color=blue>**3. UDP通信程序练习**</font>

- **案例需求**

  UDP发送数据：数据来自于键盘录入，直到输入的数据是886，发送数据结束

  UDP接收数据：因为接收端不知道发送端什么时候停止发送，故采用死循环接收

- **代码实现**

  ```java
  public class SendDemo {
      public static void main(String[] args) throws IOException {
          //1. 创建发送端的Socket对象(DatagramSocket)
          DatagramSocket ds = new DatagramSocket();
          //2. 键盘录入数据
          Scanner sc = new Scanner(System.in);
          while (true) {
              System.out.println("请输入您要说的话：");
            	String s = sc.nextLine();
              //输入的数据是886，发送数据结束
              if ("886".equals(s)) {
                  break;
              }
              //3. 创建数据，并把数据打包
              byte[] bys = s.getBytes();
              DatagramPacket dp = new DatagramPacket(bys, bys.length, InetAddress.getByName("192.168.1.66"), 12345);
  
              //4. 调用DatagramSocket对象的方法发送数据
              ds.send(dp);
          }
          //5. 关闭发送端
          ds.close();
      }
  }
  
  public class ReceiveDemo {
      public static void main(String[] args) throws IOException {
          //1. 创建接收端的Socket对象(DatagramSocket)
          DatagramSocket ds = new DatagramSocket(12345);
          while (true) {
              //2. 创建一个数据包，用于接收数据
              byte[] bys = new byte[1024];
              DatagramPacket dp = new DatagramPacket(bys, bys.length);
              ds.receive(dp);
              //3. 解析数据包，并把数据在控制台显示
              System.out.println("数据是：" + new String(dp.getData(), 0, dp.getLength()));
          }
          //4. 关闭接收端
  //        ds.close();
      }
  }
  ```

- 设置发送端可运行多个：设置Run/Debug Configuration，设置Add Run Options(Allow multiple instances)



### 2.2 UDP三种通讯方式

- **单播**：两个主机之间的端对端通信

- **组播**：对一组特定的主机进行通信(组播地址：224.0.0.0 - 239.255.255.255，其中224.0.0.0-224.0.0.255为预设的组播地址)

- **广播**：一个主机对整个局域网上所有主机上的数据通信(广播地址：255.255.255.255)

<font color=blue>**1. UDP组播实现**</font>

- **实现步骤**

  - 发送端
    1. 创建发送端的Socket对象(DatagramSocket)
    2. 创建数据，并把数据打包(DatagramPacket)
    3. 调用DatagramSocket对象的方法发送数据(在单播中,这里是发给指定IP的电脑但是在组播当中,这里是发给组播地址)
    4. 释放资源
  - 接收端
    1. 创建接收端Socket对象(MulticastSocket)
    2. 创建一个箱子,用于接收数据
    3. 把当前计算机绑定一个组播地址
    4. 将数据接收到箱子中
    5. 解析数据包,并打印数据
    6. 释放资源

- **代码实现**

  ```java
  // 发送端
  public class ClinetDemo {
      public static void main(String[] args) throws IOException {
          // 1. 创建发送端的Socket对象(DatagramSocket)
          DatagramSocket ds = new DatagramSocket();
          String s = "hello 组播";
          byte[] bytes = s.getBytes();
          InetAddress address = InetAddress.getByName("224.0.1.0"); //组播地址
          int port = 10000;
          // 2. 创建数据，并把数据打包(DatagramPacket)
          DatagramPacket dp = new DatagramPacket(bytes,bytes.length,address,port);
          // 3. 调用DatagramSocket对象的方法发送数据(在单播中,这里是发给指定IP的电脑但是在组播当中,这里是发给组播地址)
          ds.send(dp);
          // 4. 释放资源
          ds.close();
      }
  }
  // 接收端
  public class ServerDemo {
      public static void main(String[] args) throws IOException {
          // 1. 创建接收端Socket对象(MulticastSocket)
          MulticastSocket ms = new MulticastSocket(10000);
          // 2. 创建一个箱子,用于接收数据
          DatagramPacket dp = new DatagramPacket(new byte[1024],1024);
          // 3. 把当前计算机绑定一个组播地址,表示添加到这一组中.
          ms.joinGroup(InetAddress.getByName("224.0.1.0"));
          // 4. 将数据接收到箱子中
          ms.receive(dp);
          // 5. 解析数据包,并打印数据
          byte[] data = dp.getData();
          int length = dp.getLength();
          System.out.println(new String(data,0,length));
          // 6. 释放资源
          ms.close();
      }
  }
  ```

<font color=blue>**2. UDP广播实现**</font>

- **实现步骤**

  - 发送端
    1. 创建发送端Socket对象(DatagramSocket)
    2. 创建存储数据的箱子,将广播地址封装进去
    3. 发送数据
    4. 释放资源
  - 接收端
    1. 创建接收端的Socket对象(DatagramSocket)
    2. 创建一个数据包，用于接收数据
    3. 调用DatagramSocket对象的方法接收数据
    4. 解析数据包，并把数据在控制台显示
    5. 关闭接收端

- **代码实现**

  ```java
  // 发送端
  public class ClientDemo {
      public static void main(String[] args) throws IOException {
        	// 1. 创建发送端Socket对象(DatagramSocket)
          DatagramSocket ds = new DatagramSocket();
  		// 2. 创建存储数据的箱子,将广播地址封装进去
          String s = "广播 hello";
          byte[] bytes = s.getBytes();
          InetAddress address = InetAddress.getByName("255.255.255.255"); //广播地址
          int port = 10000;
          DatagramPacket dp = new DatagramPacket(bytes,bytes.length,address,port);
  		// 3. 发送数据
          ds.send(dp);
  		// 4. 释放资源
          ds.close();
      }
  }
  
  // 接收端
  public class ServerDemo {
      public static void main(String[] args) throws IOException {
          // 1. 创建接收端的Socket对象(DatagramSocket)
          DatagramSocket ds = new DatagramSocket(10000);
          // 2. 创建一个数据包，用于接收数据
          DatagramPacket dp = new DatagramPacket(new byte[1024],1024);
          // 3. 调用DatagramSocket对象的方法接收数据
          ds.receive(dp);
          // 4. 解析数据包，并把数据在控制台显示
          byte[] data = dp.getData();
          int length = dp.getLength();
          System.out.println(new String(data,0,length));
          // 5. 关闭接收端
          ds.close();
      }
  }
  ```



## 3 TCP通信程序

<font color=blue>**1. TCP发送数据**</font>

- **Java中的TCP通信**

  - Java对基于TCP协议的的网络提供了良好的封装，使用Socket对象来代表两端的通信端口，并通过Socket产生IO流来进行网络通信。
  - Java为客户端提供了Socket类，为服务器端提供了ServerSocket类
  - TCP通信前要保证连接已经建立，通过Socket产生IO流来进行网络通信

- **构造方法**

  | 方法名                               | 说明                                           |
  | ------------------------------------ | ---------------------------------------------- |
  | Socket(InetAddress address,int port) | 创建流套接字并将其连接到指定IP指定端口号       |
  | Socket(String host, int port)        | 创建流套接字并将其连接到指定主机上的指定端口号 |

- **相关方法**

  | 方法名                         | 说明                 |
  | ------------------------------ | -------------------- |
  | InputStream  getInputStream()  | 返回此套接字的输入流 |
  | OutputStream getOutputStream() | 返回此套接字的输出流 |

- **示例代码**

  ```java
  //发送数据
  public class Client {
      public static void main(String[] args) throws IOException {
         //1.创建Socket对象
          //细节：在创建对象的同时会连接服务端，如果连接不上，代码会报错
          Socket socket = new Socket("127.0.0.1",10000); 
  
          //2.可以从连接通道中获取输出流
          OutputStream os = socket.getOutputStream();
          //写出数据
          os.write("aaa".getBytes());
  
          //3.释放资源
          os.close();
          socket.close();
      }
  }
  ```

<font color=blue>**2. TCP接收数据**</font>

- **构造方法**

  | 方法名                  | 说明                             |
  | ----------------------- | -------------------------------- |
  | ServletSocket(int port) | 创建绑定到指定端口的服务器套接字 |

- **相关方法**

  | 方法名          | 说明                           |
  | --------------- | ------------------------------ |
  | Socket accept() | 监听要连接到此的套接字并接受它 |

- **注意事项**

  1. accept方法是阻塞的,作用就是等待客户端连接
  2. 客户端创建对象并连接服务器,此时是通过三次握手协议,保证跟服务器之间的连接
  3. 针对客户端来讲,是往外写的,所以是输出流
     针对服务器来讲,是往里读的,所以是输入流
  4. read方法也是阻塞的
  5. 客户端在关流的时候,还多了一个往服务器写结束标记的动作
  6. 最后一步断开连接,通过四次挥手协议保证连接终止

- **三次握手和四次挥手**

  - **三次握手** --- 确保连接建立

    - 客户端向服务器发出连接请求(等待服务器确认)

    - 服务器向客户端返回一个响应(告诉客户端收到了请求)

    - 客户端向服务器再次发出确认信息(连接建立)

  - **四次挥手** --- 确保连接断开，且数据处理完毕

    ![08_TCP四次挥手](javaBasis_assets\08_TCP四次挥手.png)

- **示例代码**

  ```java
  //接收数据
  public class Server {
      public static void main(String[] args) throws IOException {
          //1.创建对象ServerSocker
          ServerSocket ss = new ServerSocket(10000);
  
          //2.监听客户端的链接
          Socket socket = ss.accept();
  
          //3.从连接通道中获取输入流读取数据
          InputStream is = socket.getInputStream();
          int b;
          while ((b = is.read()) != -1){
              System.out.println((char) b);
          }
  
          //4.释放资源
          socket.close();
          ss.close();
      }
  }
  ```

<font color=blue>**3. 中文乱码问题**</font>

**发送端**：

```java
public class Client {
    public static void main(String[] args) throws IOException {
        //1.创建Socket对象
        //细节：在创建对象的同时会连接服务端
        //      如果连接不上，代码会报错
        Socket socket = new Socket("127.0.0.1",10000);

        //2.可以从连接通道中获取输出流
        OutputStream os = socket.getOutputStream();
        //写出数据
        os.write("你好你好".getBytes());//12字节

        //3.释放资源
        os.close();
        socket.close();
    }
}
```

**接收端：**

```java
public class Server {
    public static void main(String[] args) throws IOException {
        //1.创建对象ServerSocker
        ServerSocket ss = new ServerSocket(10000);

        //2.监听客户端的链接
        Socket socket = ss.accept();

        //3.从连接通道中获取输入流读取数据
        InputStream is = socket.getInputStream();
        InputStreamReader isr = new InputStreamReader(is);//转换为字符流
        BufferedReader br = new BufferedReader(isr);

        // BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));

        int b;
        while ((b = br.read()) != -1){
            System.out.print((char) b);
        }

        //4.释放资源
        socket.close();
        ss.close();
    }
}
```

## 4. 综合练习

### 练习一：多发多收

需求：

​	客户端：多次发送数据

​	服务器：接收多次接收数据，并打印

代码示例：

```java
public class Client {
    public static void main(String[] args) throws IOException {
        //客户端：多次发送数据
        //服务器：接收多次接收数据，并打印

        //1. 创建Socket对象并连接服务端
        Socket socket = new Socket("127.0.0.1",10000);

        //2.写出数据
        Scanner sc = new Scanner(System.in);
        OutputStream os = socket.getOutputStream();

        while (true) {
            System.out.println("请输入您要发送的信息");
            String str = sc.nextLine();
            if("886".equals(str)){
                break;
            }
            os.write(str.getBytes());
        }
        //3.释放资源
        socket.close();
    }
}
```

```java
public class Server {
    public static void main(String[] args) throws IOException {
        //客户端：多次发送数据
        //服务器：接收多次接收数据，并打印

        //1.创建对象绑定10000端口
        ServerSocket ss = new ServerSocket(10000);

        //2.等待客户端来连接
        Socket socket = ss.accept();

        //3.读取数据
        InputStreamReader isr = new InputStreamReader(socket.getInputStream());
        int b;
        while ((b = isr.read()) != -1){
            System.out.print((char)b);
        }

        //4.释放资源
        socket.close();
        ss.close();
    }
}
```



### 练习二：接收并反馈

- 案例需求

  客户端：发送数据，接受服务器反馈

  服务器：收到消息后给出反馈

- 案例分析

  - 客户端创建对象，使用输出流输出数据
  - 服务端创建对象，使用输入流接受数据
  - 服务端使用输出流给出反馈数据
  - 客户端使用输入流接受反馈数据

- 代码实现

  ```java
  // 客户端
  public class ClientDemo {
      public static void main(String[] args) throws IOException {
          Socket socket = new Socket("127.0.0.1",10000);
  
          OutputStream os = socket.getOutputStream();
          os.write("hello".getBytes());
         // os.close();如果在这里关流,会导致整个socket都无法使用
          socket.shutdownOutput();//仅仅关闭输出流.并写一个结束标记,对socket没有任何影响
          
          BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));
          String line;
          while((line = br.readLine())!=null){
              System.out.println(line);
          }
          br.close();
          os.close();
          socket.close();
      }
  }
  // 服务器
  public class ServerDemo {
      public static void main(String[] args) throws IOException {
          ServerSocket ss = new ServerSocket(10000);
  
          Socket accept = ss.accept();
  
          InputStream is = accept.getInputStream();
          int b;
          while((b = is.read())!=-1){
              System.out.println((char) b);
          }
  
          System.out.println("看看我执行了吗?");
  
          BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(accept.getOutputStream()));
          bw.write("你谁啊?");
          bw.newLine();
          bw.flush();
  
          bw.close();
          is.close();
          accept.close();
          ss.close();
      }
  }
  ```

### 练习三：上传练习（TCP协议）

- 案例需求

  客户端：数据来自于本地文件，接收服务器反馈

  服务器：接收到的数据写入本地文件，给出反馈

- 案例分析

  - 创建客户端对象，创建输入流对象指向文件，每读一次数据就给服务器输出一次数据，输出结束后使用shutdownOutput()方法告知服务端传输结束
  - 创建服务器对象，创建输出流对象指向文件，每接受一次数据就使用输出流输出到文件中，传输结束后。使用输出流给客户端反馈信息
  - 客户端接受服务端的回馈信息

- 相关方法

  | 方法名                | 说明                               |
  | --------------------- | ---------------------------------- |
  | void shutdownInput()  | 将此套接字的输入流放置在“流的末尾” |
  | void shutdownOutput() | 禁止用此套接字的输出流             |

- 代码实现

  ```java
  public class Client {
      public static void main(String[] args) throws IOException {
          //客户端：将本地文件上传到服务器。接收服务器的反馈。
          //服务器：接收客户端上传的文件，上传完毕之后给出反馈。
  
  
          //1. 创建Socket对象，并连接服务器
          Socket socket = new Socket("127.0.0.1",10000);
  
          //2.读取本地文件中的数据，并写到服务器当中
          BufferedInputStream bis = new BufferedInputStream(new FileInputStream("mysocketnet\\clientdir\\a.jpg"));
          BufferedOutputStream bos = new BufferedOutputStream(socket.getOutputStream());
          byte[] bytes = new byte[1024];
          int len;
          while ((len = bis.read(bytes)) != -1){
              bos.write(bytes,0,len);
          }
  
          //往服务器写出结束标记
          socket.shutdownOutput();
  
  
          //3.接收服务器的回写数据
          BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));
          String line = br.readLine();
          System.out.println(line);
  
  
          //4.释放资源
          socket.close();
  
      }
  }
  ```

  ```java
  public class Server {
      public static void main(String[] args) throws IOException {
          //客户端：将本地文件上传到服务器。接收服务器的反馈。
          //服务器：接收客户端上传的文件，上传完毕之后给出反馈。
  
  
          //1.创建对象并绑定端口
          ServerSocket ss = new ServerSocket(10000);
  
          //2.等待客户端来连接
          Socket socket = ss.accept();
  
          //3.读取数据并保存到本地文件中
          BufferedInputStream bis = new BufferedInputStream(socket.getInputStream());
          BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("mysocketnet\\serverdir\\a.jpg"));
          int len;
          byte[] bytes = new byte[1024];
          while ((len = bis.read(bytes)) != -1){
              bos.write(bytes,0,len);
          }
          bos.close();
          //4.回写数据
          BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
          bw.write("上传成功");
          bw.newLine();
          bw.flush();
  
          //5.释放资源
          socket.close();
          ss.close();
      }
  }
  ```

### 练习四：文件名重复

     ```java

public class UUIDTest {
    public static void main(String[] args) {
        String str = UUID.randomUUID().toString().replace("-", "");
        System.out.println(str);//9f15b8c356c54f55bfcb0ee3023fce8a
    }
}
     ```

```java
public class Client {
    public static void main(String[] args) throws IOException {
        //客户端：将本地文件上传到服务器。接收服务器的反馈。
        //服务器：接收客户端上传的文件，上传完毕之后给出反馈。


        //1. 创建Socket对象，并连接服务器
        Socket socket = new Socket("127.0.0.1",10000);

        //2.读取本地文件中的数据，并写到服务器当中
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream("mysocketnet\\clientdir\\a.jpg"));
        BufferedOutputStream bos = new BufferedOutputStream(socket.getOutputStream());
        byte[] bytes = new byte[1024];
        int len;
        while ((len = bis.read(bytes)) != -1){
            bos.write(bytes,0,len);
        }

        //往服务器写出结束标记
        socket.shutdownOutput();


        //3.接收服务器的回写数据
        BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String line = br.readLine();
        System.out.println(line);


        //4.释放资源
        socket.close();

    }
}
```

```java
public class Server {
    public static void main(String[] args) throws IOException {
        //客户端：将本地文件上传到服务器。接收服务器的反馈。
        //服务器：接收客户端上传的文件，上传完毕之后给出反馈。


        //1.创建对象并绑定端口
        ServerSocket ss = new ServerSocket(10000);

        //2.等待客户端来连接
        Socket socket = ss.accept();

        //3.读取数据并保存到本地文件中
        BufferedInputStream bis = new BufferedInputStream(socket.getInputStream());
        String name = UUID.randomUUID().toString().replace("-", "");
        BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("mysocketnet\\serverdir\\" + name + ".jpg"));
        int len;
        byte[] bytes = new byte[1024];
        while ((len = bis.read(bytes)) != -1) {
            bos.write(bytes, 0, len);
        }
        bos.close();
        //4.回写数据
        BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
        bw.write("上传成功");
        bw.newLine();
        bw.flush();

        //5.释放资源
        socket.close();
        ss.close();
    }
}
```

### 练习五：服务器改写为多线程

服务器只能处理一个客户端请求，接收完一个图片之后，服务器就关闭了。

优化方案一：

​	使用循环

弊端：

​	第一个用户正在上传数据，第二个用户就来访问了，此时第二个用户是无法成功上传的。

​	所以，使用多线程改进

优化方案二：

​	每来一个用户，就开启多线程处理

```java
public class Client {
    public static void main(String[] args) throws IOException {
        //客户端：将本地文件上传到服务器。接收服务器的反馈。
        //服务器：接收客户端上传的文件，上传完毕之后给出反馈。


        //1. 创建Socket对象，并连接服务器
        Socket socket = new Socket("127.0.0.1",10000);

        //2.读取本地文件中的数据，并写到服务器当中
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream("mysocketnet\\clientdir\\a.jpg"));
        BufferedOutputStream bos = new BufferedOutputStream(socket.getOutputStream());
        byte[] bytes = new byte[1024];
        int len;
        while ((len = bis.read(bytes)) != -1){
            bos.write(bytes,0,len);
        }

        //往服务器写出结束标记
        socket.shutdownOutput();


        //3.接收服务器的回写数据
        BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String line = br.readLine();
        System.out.println(line);


        //4.释放资源
        socket.close();

    }
}
```

```java
public class Server {
    public static void main(String[] args) throws IOException {
        //客户端：将本地文件上传到服务器。接收服务器的反馈。
        //服务器：接收客户端上传的文件，上传完毕之后给出反馈。


        //1.创建对象并绑定端口
        ServerSocket ss = new ServerSocket(10000);

        while (true) {
            //2.等待客户端来连接
            Socket socket = ss.accept();

            //开启一条线程
            //一个用户就对应服务端的一条线程
            new Thread(new MyRunnable(socket)).start();
        }

    }
}


public class MyRunnable implements Runnable{

    Socket socket;

    public MyRunnable(Socket socket){
        this.socket = socket;
    }

    @Override
    public void run() {
        try {
            //3.读取数据并保存到本地文件中
            BufferedInputStream bis = new BufferedInputStream(socket.getInputStream());
            String name = UUID.randomUUID().toString().replace("-", "");
            BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("mysocketnet\\serverdir\\" + name + ".jpg"));
            int len;
            byte[] bytes = new byte[1024];
            while ((len = bis.read(bytes)) != -1) {
                bos.write(bytes, 0, len);
            }
            bos.close();
            //4.回写数据
            BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
            bw.write("上传成功");
            bw.newLine();
            bw.flush();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            //5.释放资源
           if(socket != null){
               try {
                   socket.close();
               } catch (IOException e) {
                   e.printStackTrace();
               }
           }
        }
    }
}
```

### 练习六：线程池改进

```java
public class Client {
    public static void main(String[] args) throws IOException {
        //客户端：将本地文件上传到服务器。接收服务器的反馈。
        //服务器：接收客户端上传的文件，上传完毕之后给出反馈。


        //1. 创建Socket对象，并连接服务器
        Socket socket = new Socket("127.0.0.1",10000);

        //2.读取本地文件中的数据，并写到服务器当中
        BufferedInputStream bis = new BufferedInputStream(new FileInputStream("mysocketnet\\clientdir\\a.jpg"));
        BufferedOutputStream bos = new BufferedOutputStream(socket.getOutputStream());
        byte[] bytes = new byte[1024];
        int len;
        while ((len = bis.read(bytes)) != -1){
            bos.write(bytes,0,len);
        }

        //往服务器写出结束标记
        socket.shutdownOutput();


        //3.接收服务器的回写数据
        BufferedReader br = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        String line = br.readLine();
        System.out.println(line);


        //4.释放资源
        socket.close();

    }
}
```

```java
public class Server {
    public static void main(String[] args) throws IOException {
        //客户端：将本地文件上传到服务器。接收服务器的反馈。
        //服务器：接收客户端上传的文件，上传完毕之后给出反馈。


        //创建线程池对象
        ThreadPoolExecutor pool = new ThreadPoolExecutor(
                3,//核心线程数量
                16,//线程池总大小
                60,//空闲时间
                TimeUnit.SECONDS,//空闲时间（单位）
                new ArrayBlockingQueue<>(2),//队列
                Executors.defaultThreadFactory(),//线程工厂，让线程池如何创建线程对象
                new ThreadPoolExecutor.AbortPolicy()//阻塞队列
        );



        //1.创建对象并绑定端口
        ServerSocket ss = new ServerSocket(10000);

        while (true) {
            //2.等待客户端来连接
            Socket socket = ss.accept();

            //开启一条线程
            //一个用户就对应服务端的一条线程
            //new Thread(new MyRunnable(socket)).start();
            pool.submit(new MyRunnable(socket));
        }

    }
}
```

```java
public class MyRunnable implements Runnable{

    Socket socket;

    public MyRunnable(Socket socket){
        this.socket = socket;
    }

    @Override
    public void run() {
        try {
            //3.读取数据并保存到本地文件中
            BufferedInputStream bis = new BufferedInputStream(socket.getInputStream());
            String name = UUID.randomUUID().toString().replace("-", "");
            BufferedOutputStream bos = new BufferedOutputStream(new FileOutputStream("mysocketnet\\serverdir\\" + name + ".jpg"));
            int len;
            byte[] bytes = new byte[1024];
            while ((len = bis.read(bytes)) != -1) {
                bos.write(bytes, 0, len);
            }
            bos.close();
            //4.回写数据
            BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
            bw.write("上传成功");
            bw.newLine();
            bw.flush();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            //5.释放资源
           if(socket != null){
               try {
                   socket.close();
               } catch (IOException e) {
                   e.printStackTrace();
               }
           }
        }
    }
}
```



## 5 反射

### 5.1 反射的基本概念

<font color=blue>**1. 什么是反射？**</font>

- 反射允许对封装类的字段，方法和构造函数的信息进行编程访问

- 利用**反射**创建的对象<font color=red>**可以无视修饰符**</font>调用类里面的内容

- 可以跟<font color=red>**配置文件结合起来使用**</font>，把要创建的对象信息和方法写在配置文件中

  - 读取到什么类，就创建什么类的对象

  - 读取到什么方法，就调用什么方法

  - 此时当需求变更的时候不需要修改代码，只要修改配置文件即可

<font color=blue>**2. 反射究竟学习什么？**</font>	

* 如何获取class字节码文件的对象

* 利用反射如何获取构造方法（创建对象）

* 利用反射如何获取成员变量（赋值，获取值）

* 利用反射如何获取成员方法（运行）

<font color=blue>**3. 获取clss对象的三种方式**</font>	

* Class这个类里面的静态方法forName（“全类名=包名+类名”）<font color=red>**Class.forName("全类名");  --- 最为常用**</font>
* 通过class属性获取  <font color=red>**类名.class --- 一般当作参数进行传递**</font>
* 通过对象获取字节码文件对象 <font color=red>**对象.getClass(); --- 当已有此类对象时使用**</font>

**代码示例**：

```java
//1.Class.forName("类的全类名")： 全类名 = 包名 + 类名
Class clazz1 = Class.forName("com.itheima.reflectdemo.Student");
//源代码阶段获取 --- 先把Student加载到内存中，再获取字节码文件的对象
//clazz 就表示Student这个类的字节码文件对象。
//就是当Student.class这个文件加载到内存之后，产生的字节码文件对象

//2.类名.class
Class clazz2 = Student.class;

//3.通过Student对象获取字节码文件对象
Student s = new Student();
Class clazz3 = s.getClass();
System.out.println(clazz1 == clazz2);//true，class文件在硬盘唯一，当这个文件加载到内存后产生的对象也是唯一的
System.out.println(clazz2 == clazz3);//true
```

<font color=blue>**4. 字节码文件和字节码文件对象**</font>	

**java文件**：自己编写的java代码

**字节码文件**：通过java文件编译之后的class文件（是在硬盘上真实存在的，用眼睛能看到的）

**字节码文件对象**：当class文件加载到内存之后，虚拟机自动创建出来的对象。

​				这个对象里面至少包含了：构造方法，成员变量，成员方法。

==反射获取的是什么？==字节码文件对象，这个对象在内存中是**唯一**的。

<font color=blue>**5. 反射的作用**</font>

- 获取一个类中所有的信息，获取到后，再执行其他的业务逻辑

- 结合配置文件，动态的创建对象并调用方法



### 5.2 获取构造方法

<font color=blue>**1. Class类中用于获取构造方法的方法**</font>	

**规则**：

​	get表示获取

​	Declared表示私有

​	最后的s表示所有，复数形式

​	如果当前获取到的是私有的，必须要临时修改访问权限，否则无法使用

| 方法名                                                       | 说明                                   |
| ------------------------------------------------------------ | -------------------------------------- |
| Constructor<?>[] getConstructors()                           | 返回所有public修饰的构造方法对象的数组 |
| Constructor<?>[] getDeclaredConstructors()                   | 返回所有的构造方法对象的数组           |
| Constructor<T> getConstructor(Class<?>... parameterTypes)    | 返回单个public修饰的构造方法对象       |
| Constructor<T> getDeclaredConstructor(Class<?>... parameterTypes) | 返回单个构造方法对象                   |

<font color=blue>**2. Constructor类中用于创建对象的方法**</font>

| 方法名                            | 说明                        |
| --------------------------------- | --------------------------- |
| T newInstance(Object... initargs) | 根据指定的构造方法创建对象  |
| setAccessible(boolean flag)       | 设置为true,表示取消访问检查 |

**代码示例**：

```java
public class ReflectDemo2 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException {
        //1.获得整体（class字节码文件对象）
        Class clazz = Class.forName("com.itheima.reflectdemo.Student");

        //2.获取构造方法对象
        Constructor[] constructors1 = clazz.getConstructors();
        for (Constructor constructor : constructors1) {
            System.out.println(constructor);
        }

        //3.获取所有构造（带私有的）
        Constructor[] constructors2 = clazz.getDeclaredConstructors();
        for (Constructor constructor : constructors2) {
            System.out.println(constructor);
        }

        //4.获取指定的空参构造
        Constructor con1 = clazz.getConstructor();
        System.out.println(con1);
        Constructor con2 = clazz.getConstructor(String.class,int.class);
        System.out.println(con2);

        //5. 获取指定的构造(所有构造都可以获取到，包括public包括private)
        Constructor con3 = clazz.getDeclaredConstructor();
        System.out.println(con3);
        //了解 System.out.println(con3 == con1);
        //每一次获取构造方法对象的时候，都会新new一个。

        Constructor con4 = clazz.getDeclaredConstructor(String.class);
        System.out.println(con4);
    }
}
```

<font color=blue>**3. 获取构造方法并创建对象**</font>

```java
//首先要有一个javabean类
public class Student {
    private String name;
    private int age;
    public Student() {}
    public Student(String name) {this.name = name;}
    private Student(String name, int age) {this.name = name;this.age = age;}
    
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public int getAge() {return age;}
    public void setAge(int age) {this.age = age;}
    public String toString() {
        return "Student{name = " + name + ", age = " + age + "}";
    }
}

//测试类中的代码：
//需求1：
//获取空参，并创建对象
//1.获取整体的字节码文件对象
Class clazz = Class.forName("com.itheima.a02reflectdemo1.Student");
//2.获取空参的构造方法
Constructor con = clazz.getConstructor();
//3.利用空参构造方法创建对象
Student stu = (Student) con.newInstance();
System.out.println(stu);

//需求2：
//获取带参构造，并创建对象
//1.获取整体的字节码文件对象
Class clazz = Class.forName("com.itheima.a02reflectdemo1.Student");
//2.获取有参构造方法
Constructor con = clazz.getDeclaredConstructor(String.class, int.class);
//3.临时修改构造方法的访问权限（暴力反射）
con.setAccessible(true);
//4.直接创建对象
Student stu = (Student) con.newInstance("zhangsan", 23);
System.out.println(stu);
```



### 5.3 获取成员变量

<font color=blue>**1. Class类中用于获取成员变量的方法**</font>	

**规则：**

​	get表示获取

​	Declared表示私有

​	最后的s表示所有，复数形式

​	如果当前获取到的是私有的，必须要临时修改访问权限，否则无法使用

| 方法名                              | 说明                                         |
| ----------------------------------- | -------------------------------------------- |
| Field[] getFields()                 | 返回所有成员变量对象的数组（只能拿public的） |
| Field[] getDeclaredFields()         | 返回所有成员变量对象的数组，存在就能拿到     |
| Field getField(String name)         | 返回单个成员变量对象（只能拿public的）       |
| Field getDeclaredField(String name) | 返回单个成员变量对象，存在就能拿到           |

**代码示例：**

```java
public class ReflectDemo4 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchFieldException {
	    //1.获取class对象
        Class clazz = Class.forName("com.itheima.reflectdemo.Student");

        //2.获取成员变量的对象（Field对象)只能获取public修饰的
        Field[] fields1 = clazz.getFields();
        for (Field field : fields1) {
            System.out.println(field);
        }
        
        //3. 获取成员变量的对象（public + private）
        Field[] fields2 = clazz.getDeclaredFields();
        for (Field field : fields2) {
            System.out.println(field);
        }

        //4. 获得单个成员变量对象
        //如果获取的属性是不存在的，那么会报异常
        //Field field3 = clazz.getField("aaa");
        //System.out.println(field3);//NoSuchFieldException

        Field field4 = clazz.getField("gender");
        System.out.println(field4);

        //5. 获取单个成员变量（私有）
        Field field5 = clazz.getDeclaredField("name");
        System.out.println(field5);
    }
}
```

<font color=blue>**2. 获取成员变量并获取值和修改值**</font>

| 方法                                | 说明   |
| ----------------------------------- | ------ |
| void set(Object obj, Object value） | 赋值   |
| Object get(Object obj)              | 获取值 |

**代码示例**：

```java
public class ReflectDemo5 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchFieldException, IllegalAccessException {
        Student s = new Student("zhangsan",23,"广州");
        Student ss = new Student("lisi",24,"北京");

        //需求：利用反射获取成员变量并获取值和修改值

        //1.获取class对象
        Class clazz = Class.forName("com.itheima.reflectdemo.Student");

        //2.获取name成员变量
        //field就表示name这个属性的对象
        Field field = clazz.getDeclaredField("name");
        //临时修饰他的访问权限
        field.setAccessible(true);

        //3.设置(修改)name的值
        //参数一：表示要修改哪个对象的name？
        //参数二：表示要修改为多少？
        field.set(s,"wangwu");

        //3.获取name的值
        //表示我要获取这个对象的name的值
        String result = (String)field.get(s);

        //4.打印结果
        System.out.println(result);

        System.out.println(s);
        System.out.println(ss);
    }
}
```



### 5.4 获取成员方法

<font color=blue>**1. 获取成员方法**</font>	

**规则**：

​	get表示获取

​	Declared表示私有

​	最后的s表示所有，复数形式

​	如果当前获取到的是私有的，必须要临时修改访问权限，否则无法使用

| 方法名                                                       | 说明                                         |
| ------------------------------------------------------------ | -------------------------------------------- |
| Method[] getMethods()                                        | 返回所有成员方法对象的数组（只能拿public的） |
| Method[] getDeclaredMethods()                                | 返回所有成员方法对象的数组，存在就能拿到     |
| Method getMethod(String name, Class<?>... parameterTypes)    | 返回单个成员方法对象（只能拿public的）       |
| Method getDeclaredMethod(String name, Class<?>... parameterTypes) | 返回单个成员方法对象，存在就能拿到           |

**代码示例**：

```java
public class ReflectDemo6 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException {
        //1.获取class对象
        Class clazz = Class.forName("com.itheima.reflectdemo.Student");

        //2.获取方法，可以获取父类中public修饰的方法
        Method[] methods1 = clazz.getMethods();
        for (Method method : methods1) {
            System.out.println(method);
        }

        //获取所有的方法（包含私有），但是只能获取自己类中的方法
        Method[] methods2 = clazz.getDeclaredMethods();
        for (Method method : methods2) {
            System.out.println(method);
        }

        //获取指定的方法（空参）
        Method method3 = clazz.getMethod("sleep");
        System.out.println(method3);
        Method method4 = clazz.getMethod("eat",String.class);
        System.out.println(method4);

        //获取指定的私有方法
        Method method5 = clazz.getDeclaredMethod("playGame");
        System.out.println(method5);
    }
}
```

<font color=blue>**2. 获取成员方法并运行**</font>

**方法：**

<font color=red> **Object invoke(Object obj, Object... args)**</font> ：运行方法

参数一：用obj对象调用该方法

参数二：调用方法的传递的参数（如果没有就不写）

返回值：方法的返回值（如果没有就不写）

**代码示例**：

```java
package com.itheima.a02reflectdemo1;

import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

public class ReflectDemo6 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        //1.获取字节码文件对象
        Class clazz = Class.forName("com.itheima.a02reflectdemo1.Student");
		
        //2.获取一个对象，需要用这个对象去调用方法
        Student s = new Student();
        
        //3.获取一个指定的方法
        //参数一：方法名
        //参数二：参数列表，如果没有可以不写
        Method eatMethod = clazz.getMethod("eat",String.class);
        
        //运行
        //参数一：表示方法的调用对象
        //参数二：方法在运行时需要的实际参数
        //注意点：如果方法有返回值，那么需要接收invoke的结果
        //如果方法没有返回值，则不需要接收
        String result = (String) eatMethod.invoke(s, "重庆小面");
        System.out.println(result);
    }
}

public class Student {
    private String name;
    private int age;
    public String gender;
    public String address;
    
    public Student() {}
    public Student(String name) {this.name = name;}
    private Student(String name, int age) {this.name = name;this.age = age;}
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public int getAge() {return age;}
    public void setAge(int age) {this.age = age;}
    public String toString() {return "Student{name = " + name + ", age = " + age + "}";}

    private void study(){System.out.println("学生在学习");}
    private void sleep(){System.out.println("学生在睡觉");}
    public String eat(String something){
        System.out.println("学生在吃" + something);
        return "学生已经吃完了，非常happy";
    }
}
```

###### 面试题：你觉得反射好不好？

好，有两个方向。

第一个方向：无视修饰符访问类中的内容。但是这种操作在开发中一般不用，都是框架底层来用的。

第二个方向：反射可以跟配置文件结合起来使用，动态的创建对象，动态的调用方法。



### 5.5 反射相关练习

<font color=blue>**1. 泛型擦除**</font>

理解：集合中的泛型只在java文件中存在，当编译成class文件之后，就没有泛型了

代码示例：（了解）

```java
package com.itheima.reflectdemo;

import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;
import java.util.ArrayList;

public class ReflectDemo8 {
    public static void main(String[] args) throws NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        //1.创建集合对象
        ArrayList<Integer> list = new ArrayList<>();
        list.add(123);
//        list.add("aaa");

        //2.利用反射运行add方法去添加字符串
        //因为反射使用的是class字节码文件

        //获取class对象
        Class clazz = list.getClass();

        //获取add方法对象
        Method method = clazz.getMethod("add", Object.class);

        //运行方法
        method.invoke(list,"aaa");

        //打印集合
        System.out.println(list);
    }
}
```

<font color=blue>**2. 修改字符串的内容**</font>

字符串，在底层是一个byte类型的字节数组，名字叫做value

```java
private final byte[] value;
```

真正不能被修改的原因：**final和private**

- final修饰value表示value记录的地址值不能修改。
- private修饰value而且没有对外提供getvalue和setvalue的方法。所以，在外界不能获取或修改value记录的地址值。

如果要强行修改可以用反射：

代码示例：（了解）

```java
String s = "abc";
String ss = "abc";
// private final byte[] value= {97,98,99};
// 没有对外提供getvalue和setvalue的方法，不能修改value记录的地址值
// 如果我们利用反射获取了value的地址值。
// 也是可以修改的，final修饰的value
// 真正不可变的value数组的地址值，里面的内容利用反射还是可以修改的，比较危险

//1.获取class对象
Class clazz = s.getClass();

//2.获取value成员变量（private）
Field field = clazz.getDeclaredField("value");
//但是这种操作非常危险
//JDK高版本已经屏蔽了这种操作，低版本还是可以的
//临时修改权限
field.setAccessible(true);

//3.获取value记录的地址值
byte[] bytes = (byte[]) field.get(s);
bytes[0] = 100;

System.out.println(s);//dbc
System.out.println(ss);//dbc
```

<font color=blue>**3. 反射和配置文件结合动态获取**</font>

需求: 利用反射根据文件中的不同类名和方法名，创建不同的对象并调用方法。

①通过Properties加载配置文件

②得到类名和方法名

③通过类名反射得到Class对象

④通过Class对象创建一个对象

⑤通过Class对象得到方法

⑥调用方法

代码示例：

```java
public class ReflectDemo9 {
    public static void main(String[] args) throws IOException, ClassNotFoundException, NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {
        //1.读取配置文件的信息
        Properties prop = new Properties();
        FileInputStream fis = new FileInputStream("day14-code\\prop.properties");
        prop.load(fis);
        fis.close();
        System.out.println(prop);

        String classname = prop.get("classname") + "";
        String methodname = prop.get("methodname") + "";

        //2.获取字节码文件对象
        Class clazz = Class.forName(classname);

        //3.要先创建这个类的对象
        Constructor con = clazz.getDeclaredConstructor();
        con.setAccessible(true);
        Object o = con.newInstance();
        System.out.println(o);

        //4.获取方法的对象
        Method method = clazz.getDeclaredMethod(methodname);
        method.setAccessible(true);

        //5.运行方法
        method.invoke(o);
    }
}

配置文件中的信息：
classname=com.itheima.a02reflectdemo1.Student
methodname=sleep
```

<font color=blue>**4. 利用发射保存对象中的信息**</font>（重点）

要求：对于任意一个对象，都可以把对象所有的字段名和值，保存到文件中去

```java
public class MyReflectDemo {
    public static void main(String[] args) throws IllegalAccessException, IOException {
       Student s = new Student("小A",23,'女',167.5,"睡觉");
       Teacher t = new Teacher("播妞",10000);
       saveObject(s);
    }

    //把对象里面所有的成员变量名和值保存到本地文件中
    public static void saveObject(Object obj) throws IllegalAccessException, IOException{
        //1.获取字节码文件的对象
        Class clazz = obj.getClass();
        //2. 创建IO流
        BufferedWriter bw = new BufferedWriter(new FileWriter("myreflect\\a.txt"));
        //3. 获取所有的成员变量
        Field[] fields = clazz.getDeclaredFields();
        for (Field field : fields) {
            field.setAccessible(true);
            //获取成员变量的名字
            String name = field.getName();
            //获取成员变量的值
            Object value = field.get(obj);
            //写出数据
            bw.write(name + "=" + value);
            bw.newLine();
        }
        bw.close();
    }
}
```

```java
public class Student {
    private String name;
    private int age;
    private char gender;
    private double height;
    private String hobby;

    public Student() {}
    public Student(String name, int age, char gender, double height, String hobby) {
        this.name = name;
        this.age = age;
        this.gender = gender;
        this.height = height;
        this.hobby = hobby;
    }
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public int getAge() {return age;}
    public void setAge(int age) {this.age = age;}
    public char getGender() {return gender;}
    public void setGender(char gender) {this.gender = gender;}
    public double getHeight() {return height;}
    public void setHeight(double height) {this.height = height;}
    public String getHobby() {return hobby;}
    public void setHobby(String hobby) {this.hobby = hobby;}
    public String toString() {
        return "Student{name = " + name + ", age = " + age + ", gender = " + gender + ", height = " + height + ", hobby = " + hobby + "}";
    }
}
```

```java
public class Teacher {
    private String name;
    private double salary;

    public Teacher() {}
    public Teacher(String name, double salary) {this.name = name;this.salary = salary;}
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public double getSalary() {return salary;}
    public void setSalary(double salary) {this.salary = salary;}
    public String toString() {
        return "Teacher{name = " + name + ", salary = " + salary + "}";
    }
}
```



## 6 动态代理

<font color=blue>**1. 动态代理的优点**</font>：<font color=red>**无侵入式**</font>的给方法增强功能

**调用者 --> 代理 --> 对象**

<font color=blue>**2. 动态代理三要素**</font>：

- 真正干活的对象
- 代理对象
- 利用代理调用方法

==注意==：代理可增强/拦截的方法都在接口中，接口需要写在newProxyInstance的第二个参数里

<font color=blue>**3. 代码实现**</font>：

```java
public class Test {
    public static void main(String[] args) {
    /*需求：外面的人想要大明星唱一首歌
     1. 获取代理的对象
                代理对象 = ProxyUtil.createProxy(大明星的对象);
     2. 再调用代理的唱歌方法
                代理对象.唱歌的方法("只因你太美");*/
        //1. 获取代理的对象
        BigStar bigStar = new BigStar("鸡哥");
        Star proxy = ProxyUtil.createProxy(bigStar);

        //2. 调用唱歌的方法
        String result = proxy.sing("只因你太美");
        System.out.println(result);
    }
}
```

```java
/*类的作用：创建一个代理*/
public class ProxyUtil {
    /*方法的作用：给一个明星的对象，创建一个代理
    * 形参：被代理的明星对象
    * 返回值：给明星创建的代理
      需求：
    *   外面的人想要大明星唱一首歌
    *   1. 获取代理的对象
    *      代理对象 = ProxyUtil.createProxy(大明星的对象);
    *   2. 再调用代理的唱歌方法
    *      代理对象.唱歌的方法("只因你太美"); */
    
    public static Star createProxy(BigStar bigStar){
       /* java.lang.reflect.Proxy类：提供了为对象产生代理对象的方法：
        public static Object newProxyInstance(ClassLoader loader, Class<?>[] interfaces, InvocationHandler h)
        参数一：用于指定用哪个类加载器，去加载生成的代理类
        参数二：指定接口，这些接口用于指定生成的代理长什么，也就是有哪些方法
        参数三：用来指定生成的代理对象要干什么事情*/
        Star star = (Star) Proxy.newProxyInstance(
                ProxyUtil.class.getClassLoader(),//参数一
                new Class[]{Star.class},//参数二
                //参数三
                new InvocationHandler() {
                    @Override
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        /*
                        * 参数一：代理的对象
                        * 参数二：要运行的方法 sing
                        * 参数三：调用sing方法时，传递的实参
                        * */
                        if("sing".equals(method.getName())){
                            System.out.println("准备话筒，收钱");
                        }else if("dance".equals(method.getName())){
                            System.out.println("准备场地，收钱");
                        }
                        //去找大明星开始唱歌或者跳舞
                        //代码的表现形式：调用大明星里面唱歌或者跳舞的方法
                        return method.invoke(bigStar,args);
                    }
                }
        );
        return star;
    }
}
```

```java
public interface Star {
    //可以把所有想要被代理的方法定义在接口当中
    //唱歌
    public abstract String sing(String name);
    //跳舞
    public abstract void dance();
}
```

```java
public class BigStar implements Star {
    private String name;

    public BigStar() {}
    public BigStar(String name) {this.name = name;}

    //唱歌
    @Override
    public String sing(String name){
        System.out.println(this.name + "正在唱" + name);
        return "谢谢";
    }
    //跳舞
    @Override
    public void dance(){System.out.println(this.name + "正在跳舞");}

    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public String toString() {return "BigStar{name = " + name + "}";
    }
}
```

## 2.4 额外扩展

动态代理，还可以拦截方法

比如：

​	在这个故事中，经济人作为代理，如果别人让邀请大明星去唱歌，打篮球，经纪人就增强功能。

​	但是如果别人让大明星去扫厕所，经纪人就要拦截，不会去调用大明星的方法。

```java
/*
* 类的作用：
*       创建一个代理
* */
public class ProxyUtil {
    public static Star createProxy(BigStar bigStar){
        public static Object newProxyInstance(ClassLoader loader, Class<?>[] interfaces, InvocationHandler h)
        Star star = (Star) Proxy.newProxyInstance(
                ProxyUtil.class.getClassLoader(),
                new Class[]{Star.class},
                new InvocationHandler() {
                    @Override
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        if("cleanWC".equals(method.getName())){
                            System.out.println("拦截，不调用大明星的方法");
                            return null;
                        }
                        //如果是其他方法，正常执行
                        return method.invoke(bigStar,args);
                    }
                }
        );
        return star;
    }
}
```

## 2.5 动态代理的练习

​	 对add方法进行增强，对remove方法进行拦截，对其他方法不拦截也不增强

```java
public class MyProxyDemo1 {
    public static void main(String[] args) {
        //动态代码可以增强也可以拦截
        //1.创建真正干活的人
        ArrayList<String> list = new ArrayList<>();

        //2.创建代理对象
        //参数一：类加载器。当前类名.class.getClassLoader()
        //                 找到是谁，把当前的类，加载到内存中了，我再麻烦他帮我干一件事情，把后面的代理类，也加载到内存

        //参数二：是一个数组，在数组里面写接口的字节码文件对象。
        //                  如果写了List，那么表示代理，可以代理List接口里面所有的方法，对这些方法可以增强或者拦截
        //                  但是，一定要写ArrayList真实实现的接口
        //                  假设在第二个参数中，写了MyInter接口，那么是错误的。
        //                  因为ArrayList并没有实现这个接口，那么就无法对这个接口里面的方法，进行增强或拦截
        //参数三：用来创建代理对象的匿名内部类
        List proxyList = (List) Proxy.newProxyInstance(
                //参数一：类加载器
                MyProxyDemo1.class.getClassLoader(),
                //参数二：是一个数组，表示代理对象能代理的方法范围
                new Class[]{List.class},
                //参数三：本质就是代理对象
                new InvocationHandler() {
                    @Override
                    //invoke方法参数的意义
                    //参数一：表示代理对象，一般不用（了解）
                    //参数二：就是方法名，我们可以对方法名进行判断，是增强还是拦截
                    //参数三：就是下面第三步调用方法时，传递的参数。
                    //举例1：
                    //list.add("阿玮好帅");
                    //此时参数二就是add这个方法名
                    //此时参数三 args[0] 就是 阿玮好帅
                    //举例2：
                    //list.set(1, "aaa");
                    //此时参数二就是set这个方法名
                    //此时参数三  args[0] 就是 1  args[1]"aaa"
                    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                        //对add方法做一个增强，统计耗时时间
                        if (method.getName().equals("add")) {
                            long start = System.currentTimeMillis();
                            //调用集合的方法，真正的添加数据
                            method.invoke(list, args);
                            long end = System.currentTimeMillis();
                            System.out.println("耗时时间：" + (end - start));
                            //需要进行返回，返回值要跟真正增强或者拦截的方法保持一致
                            return true;
                        }else if(method.getName().equals("remove") && args[0] instanceof Integer){
                            System.out.println("拦截了按照索引删除的方法");
                            return null;
                        }else if(method.getName().equals("remove")){
                            System.out.println("拦截了按照对象删除的方法");
                            return false;
                        }else{
                            //如果当前调用的是其他方法,我们既不增强，也不拦截
                            method.invoke(list,args);
                            return null;
                        }
                    }
                }
        );

        //3.调用方法
        //如果调用者是list，就好比绕过了第二步的代码，直接添加元素
        //如果调用者是代理对象，此时代理才能帮我们增强或者拦截

        //每次调用方法的时候，都不会直接操作集合
        //而是先调用代理里面的invoke，在invoke方法中进行判断，可以增强或者拦截
        proxyList.add("aaa");
        proxyList.add("bbb");
        proxyList.add("ccc");
        proxyList.add("ddd");

        proxyList.remove(0);
        proxyList.remove("aaa");


        //打印集合
        System.out.println(list);
    }
}
```

