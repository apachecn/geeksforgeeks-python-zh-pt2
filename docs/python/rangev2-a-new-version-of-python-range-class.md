# range v2–Python 范围类的新版本

> 原文:[https://www . geesforgeks . org/range v2-a-新版本 python-range-class/](https://www.geeksforgeeks.org/rangev2-a-new-version-of-python-range-class/)

`[range()](https://www.geeksforgeeks.org/python-range-method/)`是 Python 的内置函数。当用户需要执行特定次数的操作时，使用它。`range()`功能用于生成一系列数字。但是由范围产生的数字序列通常不是递减就是线性递增，这意味着它不是递增就是递减一个特定的常数。

**`rangev2`模块**提供了一个功能`new_range()`，也可以通过使用`*, //, %`操作符来产生序列，这样序列就可以指数变化。

这个模块没有内置 python，所以可以通过在终端中键入下面的命令来安装。

```py
pip install rangev2

```

> **语法:** new_range(开始、停止、步进)
> 
> **参数:**
> **start–**整数，从该整数开始返回整数序列。
> **stop–**整数，在此之前返回整数序列。
> **步骤–**包含操作数和运算符的字符串。

**示例#1:**

```py
# Python Program to  
# show rangev2 basics

#Importing module
import rangev2 as r2

# program to produce Geometeric progression using rangev2
for i in r2.new_range(2, 100, '*2'):
    print(i, end=" ")
print()

# printing powers
for i in r2.new_range(2, 1000, '**2'):
    print(i, end=" ")
print()

# printing divisions
for i in r2.new_range(100,1,'//3'):
    print(i, end=" ")
```

**输出:**

```py
2 4 8 16 32 64
2 4 16 256
100 33 11 3

```

**例 2:**

```py
# Python program to produce Geometric progression using rangev2

import rangev2 as r2

a = '2'    # First number of the geometeric progression
c = '100'  # Enter the upper bond
b = '2'    # Enter the common ration

print(r2.new_range(int(a),int(c),'*' + b).list)
```

**输出:**

```py
[2,4,8,16,32,64]
```