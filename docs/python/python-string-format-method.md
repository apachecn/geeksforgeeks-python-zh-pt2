# Python 字符串格式()方法

> 原文:[https://www.geeksforgeeks.org/python-string-format-method/](https://www.geeksforgeeks.org/python-string-format-method/)

**Python format()函数**的引入是为了更高效地处理复杂的字符串格式。这个内置字符串类的方法为复杂的变量替换和值格式化提供了功能。这种新的格式化技术被认为更加优雅。format()方法的一般语法是 string.format(var1，var2，…)

## **使用单一格式化程序**

格式化程序通过将一对大括号 **{ }** 定义的一个或多个替换字段和占位符放入字符串并调用 str.format()来工作。我们希望放入占位符并与作为参数传递到 format 函数的字符串连接的值。

> **语法:** { }。格式(值)
> 
> **参数:**
> **(值):**可以是整数、浮点数字常量、字符串、字符甚至变量。
> **Returntype :** 返回一个格式化的字符串，该字符串的值在占位符位置作为参数传递。

### **示例 1:** 格式的简单演示()

## 蟒蛇 3

```
# Python3 program to demonstrate
# the str.format() method

# using format option in a simple string
print("{}, A computer science portal for geeks."
      .format("GeeksforGeeks"))

# using format option for a
# value stored in a variable
str = "This article is written in {}"
print(str.format("Python"))

# formatting a string using a numeric constant
print("Hello, I am {} years old !".format(18))
```

**输出:**

```
GeeksforGeeks, A computer science portal for geeks.
This article is written in Python
Hello, I am  18 years old!
```

## 使用多个格式化程序

格式化字符串时，可以使用多对大括号。假设句子中需要另一个变量替换，可以通过添加第二对花括号并将第二个值传递给方法来完成。Python 将以**的顺序用值替换占位符。**

> **语法:** { } { }。格式(值 1、值 2)
> 
> **参数:** **(值 1、值 2) :** 可以是整数、浮点数字常量、字符串、字符甚至变量。唯一不同的是，在 format()方法中作为参数传递的值的数量必须等于在字符串中创建的占位符的数量。
> 
> **错误和异常:**
> 
> **索引错误:**当字符串有一个额外的占位符，并且我们没有在 format()方法中为其传递任何值时发生。Python 通常会按照 *0，1，2，3 的顺序给占位符分配默认索引。*访问作为参数传递的值。因此，当它遇到一个占位符，其索引中没有任何作为参数传递的值时，它会抛出 IndexError。

### **示例 2:** Python 字符串格式()方法索引错误

## 蟒蛇 3

```
# Python program demonstrating Index error

# Number of placeholders are four but
# there are only three values passed

# parameters in format function.
my_string = "{}, is a {} {} science portal for {}"

print(my_string.format("GeeksforGeeks", "computer", "geeks"))
```

**输出:**

```
IndexError: tuple index out of range
```

### 示例 **3:** 带多个占位符的 Python 字符串格式()

## 蟒蛇 3

```
# Python program using multiple place
# holders to demonstrate str.format() method

# Multiple placeholders in format() function
my_string = "{}, is a {} science portal for {}"
print(my_string.format("GeeksforGeeks", "computer", "geeks"))

# different datatypes can be used in formatting
print("Hi ! My name is {} and I am {} years old"
      .format("User", 19))

# The values passed as parameters
# are replaced in order of their entry
print("This is {} {} {} {}"
      .format("one", "two", "three", "four"))
```

**输出:**

```
GeeksforGeeks, is a computer science portal for geeks
Hi! My name is User and I am 19 years old
This is one two three four
```

## **使用转义序列格式化字符串**

您可以在字符串中使用两个或多个特殊指定的字符来格式化字符串或执行命令。这些字符被称为转义序列。Python 中的转义序列以反斜杠(\)开头。例如，\n 是一个转义序列，在这个序列中，字母 n 的普通含义被转义，并被赋予另一个含义——一个新行。

<figure class="table">

| 转义序列 | 描述 | 例子 |
| --- | --- | --- |
| \n | 将字符串分成新行 | 印刷体(“我设计了这首韵文在适当的时候解释\所有我知道的”) |
| \t | 添加水平选项卡 | 印刷品(“时间是一件有价值的东西”) |
| \\ | 打印反斜杠 | 打印(看着钟摆摆动时它飞过) |
| \' | 打印单条报价 | 打印(“你怎么努力都没关系”) |
| \" | 打印双引号 | 印刷品(它是如此“不真实”) |
| \a | 发出像钟一样的声音 | 打印(' \a ') |

</figure>

## 带有位置和关键字参数的格式化程序

当占位符 **{ }** 为空时，Python 将按顺序替换通过 str.format()传递的值。

str.format()方法中存在的值本质上是**元组数据类型**，元组中包含的每个单个值都可以通过其索引号来调用，索引号从索引号 0 开始。这些索引号可以传递到花括号中，花括号用作原始字符串中的占位符。

> **语法:** {0} {1}。格式(位置参数、关键字参数)
> 
> **参数:** (positional_argument，keyword _ argument)
> **Positional _ argument**可以是整数、浮点数字常量、字符串、字符甚至变量。
> **Keyword_argument** 本质上是一个存储某个值的变量，作为参数传递。

### **例 4:**

## 蟒蛇 3

```
# To demonstrate the use of formatters
# with positional key arguments.

# Positional arguments
# are placed in order
print("{0} love {1}!!".format("GeeksforGeeks",
                              "Geeks"))

# Reverse the index numbers with the
# parameters of the placeholders
print("{1} love {0}!!".format("GeeksforGeeks",
                              "Geeks"))

print("Every {} should know the use of {} {} programming and {}"
      .format("programmer", "Open", "Source",
              "Operating Systems"))

# Use the index numbers of the
# values to change the order that
# they appear in the string
print("Every {3} should know the use of {2} {1} programming and {0}"
      .format("programmer", "Open", "Source", "Operating Systems"))

# Keyword arguments are called
# by their keyword name
print("{gfg} is a {0} science portal for {1}"
      .format("computer", "geeks", gfg="GeeksforGeeks"))
```

**输出:**

> 极客暴发户喜欢极客！！
> 
> 极客喜欢极客 forGeeks！！
> 
> 每个程序员都应该知道开源编程和操作系统的使用
> 
> 每个操作系统都应该知道开源编程和程序员的使用
> 
> 极客博客是极客的计算机科学门户

## 类型指定

更多的参数可以包含在我们语法的大括号中。使用格式代码语法 **{field_name:** **转换}** ，其中 *field_name* 指定 str.format()方法的参数的索引号，转换是指数据类型的转换代码。

### **示例:% s**–格式化前通过 str()进行字符串转换

## 蟒蛇 3

```
print("%20s" % ('geeksforgeeks', ))
print("%-20s" % ('Interngeeks', ))
print("%.5s" % ('Interngeeks', ))
```

**输出:**

```
       geeksforgeeks
Interngeeks         
Inter
```

### **示例:% c**–角色

## 蟒蛇 3

```
type = 'bug'

result = 'troubling'

print('I wondered why the program was %s me. Then\
it dawned on me it was a %s .' %
      (result, type))
```

**输出:**

> 我想知道为什么这个项目让我感到困扰。后来我才明白这是一只虫子。

### **示例:%i** 有符号十进制整数和 **%d** 有符号十进制整数(基数-10)

## 蟒蛇 3

```
match = 12000

site = 'amazon'

print("%s is so useful. I tried to look\
up mobile and they had a nice one that cost %d rupees." % (site, match))
```

**输出:**

> 亚马逊太有用了。我试着查找手机，他们有一个很好的手机，价格是 12000 卢比

### 另一种有用的类型指定

*   **%u** 无符号十进制整数
*   **%o** 八进制整数
*   **f**–浮点显示
*   **b**–二进制
*   **o**–八进制
*   **% x**–9 后带小写字母的十六进制
*   **% X**–9 后带大写字母的十六进制
*   **e**–指数表示法

您也可以指定格式化符号。唯一的变化是使用冒号(:)而不是% 1。例如，使用{:s}代替%s，使用(:d)代替%d

> **语法:**String { field _ name:conversion } example . format(value)
> **错误和异常:**
> **ValueError :** 此方法在类型转换时出错。

### 例 5:

## 蟒蛇 3

```
# Demonstrate ValueError while
# doing forced type-conversions

# When explicitly converted floating-point
# values to decimal with base-10 by 'd'
# type conversion we encounter Value-Error.
print("The temperature today is {0:d} degrees outside !"
      .format(35.567))

# Instead write this to avoid value-errors
''' print("The temperature today is {0:.0f} degrees outside !"
                                            .format(35.567))'''
```

**输出:**

```
ValueError: Unknown format code 'd' for object of type 'float'
```

### 示例 **6 :**

## 蟒蛇 3

```
# Convert base-10 decimal integers
# to floating point numeric constants
print("This site is {0:f}% securely {1}!!".
      format(100, "encrypted"))

# To limit the precision
print("My average of this {0} was {1:.2f}%"
      .format("semester", 78.234876))

# For no decimal places
print("My average of this {0} was {1:.0f}%"
      .format("semester", 78.234876))

# Convert an integer to its binary or
# with other different converted bases.
print("The {0} of 100 is {1:b}"
      .format("binary", 100))

print("The {0} of 100 is {1:o}"
      .format("octal", 100))
```

**输出:**

```
This site is 100.000000% securely encrypted!!
My average of this semester was 78.23%
My average of this semester was 78%
The binary of 100 is 1100100
The octal of 100 is 144
```

## 填充替换或生成空格

### 示例 7:字符串作为参数传递时的间距演示

默认情况下，字符串在字段中是左对齐的，数字是右对齐的。我们可以通过在冒号后面放置一个对齐代码来修改它。

```
<   :  left-align text in the field
^   :  center text in the field
>   :  right-align text in the field
```

## 蟒蛇 3

```
# To demonstrate spacing when
# strings are passed as parameters
print("{0:4}, is the computer science portal for {1:8}!"
      .format("GeeksforGeeks", "geeks"))

# To demonstrate spacing when numeric
# constants are passed as parameters.
print("It is {0:5} degrees outside !"
      .format(40))

# To demonstrate both string and numeric
# constants passed as parameters
print("{0:4} was founded in {1:16}!"
      .format("GeeksforGeeks", 2009))

# To demonstrate aligning of spaces
print("{0:^16} was founded in {1:<4}!"
      .format("GeeksforGeeks", 2009))

print("{:*^20s}".format("Geeks"))
```

**输出:**

```
GeeksforGeeks, is the computer science portal for geeks   !
It is    40 degrees outside!
GeeksforGeeks was founded in             2009!
 GeeksforGeeks   was founded in 2009 !
*******Geeks********
```

## 应用程序

格式化程序通常用于组织数据。当格式化程序被用来以可视化的方式组织大量数据时，可以看到它们最好的一面。如果我们向用户显示数据库，使用格式化程序来增加字段大小和修改对齐方式可以使输出更加易读。

### **例 8:** 用 format()演示大数据的组织

## 蟒蛇 3

```
# which prints out i, i ^ 2, i ^ 3,
#  i ^ 4 in the given range

# Function prints out values
# in an unorganized manner
def unorganized(a, b):
    for i in range(a, b):
        print(i, i**2, i**3, i**4)

# Function prints the organized set of values
def organized(a, b):
    for i in range(a, b):

        # Using formatters to give 6
        # spaces to each set of values
        print("{:6d} {:6d} {:6d} {:6d}"
              .format(i, i ** 2, i ** 3, i ** 4))

# Driver Code
n1 = int(input("Enter lower range :-\n"))
n2 = int(input("Enter upper range :-\n"))

print("------Before Using Formatters-------")

# Calling function without formatters
unorganized(n1, n2)

print()
print("-------After Using Formatters---------")
print()

# Calling function that contains
# formatters to organize the data
organized(n1, n2)
```

**输出:**

```
Enter lower range :-
3
Enter upper range :-
10
------Before Using Formatters-------
3 9 27 81
4 16 64 256
5 25 125 625
6 36 216 1296
7 49 343 2401
8 64 512 4096
9 81 729 6561

-------After Using Formatters---------

     3      9     27     81
     4     16     64    256
     5     25    125    625
     6     36    216   1296
     7     49    343   2401
     8     64    512   4096
     9     81    729   6561
```

## **使用字典进行字符串格式化**

使用字典将值解包到需要格式化的字符串中的占位符中。我们基本上用 ****** 来解包数值。在准备 SQL 查询时，此方法在字符串替换中非常有用。

## 蟒蛇 3

```
introduction = 'My name is {first_name} {middle_name} {last_name} AKA the {aka}.'
full_name = {
    'first_name': 'Tony',
    'middle_name': 'Howard',
    'last_name': 'Stark',
    'aka': 'Iron Man',
}

# Notice the use of "**" operator to unpack the values.
print(introduction.format(**full_name))
```

**输出:**

```
My name is Tony Howard Stark AKA the Iron Man.
```

## 带列表的 Python 格式()

给定一个浮点值列表，任务是将所有浮点值截断为 2 位小数。让我们看看完成任务的不同方法。

## 蟒蛇 3

```
# Python code to truncate float
# values to 2 decimal digits.

# List initialization
Input = [100.7689454, 17.232999, 60.98867, 300.83748789]

# Using format
Output = ['{:.2f}'.format(elem) for elem in Input]

# Print output
print(Output)
```

**输出:**

```
['100.77', '17.23', '60.99', '300.84']
```