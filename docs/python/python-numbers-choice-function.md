# Python 数字|选择()函数

> 原文:[https://www . geesforgeks . org/python-numbers-choice-function/](https://www.geeksforgeeks.org/python-numbers-choice-function/)

choice()是 Python 编程语言中的一个内置函数，它从列表、元组或字符串中返回一个随机项。

**语法:**

```
random.choice(sequence)
Parameters: 
sequence is a mandatory parameter that
can be a list, tuple, or string.
Returns:  
The choice() returns a random item. 
```

**注:** *我们要导入随机才能使用 choice()方法。*

下面是上述方法的 Python3 实现:

```
# Python3 program to demonstrate the use of
# choice() method 

# import random 
import random

# prints a random value from the list
list1 = [1, 2, 3, 4, 5, 6] 
print(random.choice(list1))

# prints a random item from the string 
string = "striver" 
print(random.choice(string))  
```

每次的输出都会有所不同，因为系统会随机返回一个项目。
**输出:**

```
5
s

```

**实际应用:**
从给定列表中打印任意随机数 5 次。

```
# Python3 program to demonstrate the practical application
# choice() 

# import random module 
import random 

list1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] 

for x in range(5):
    print(random.choice(list1))
```

每次使用 choice()函数时，输出都会改变。
输出:

```
1
4
1
5
7

```