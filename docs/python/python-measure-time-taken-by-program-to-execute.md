# Python–测量程序执行

所花费的时间

> 原文:[https://www . geesforgeks . org/python-measure-程序执行所用时间/](https://www.geeksforgeeks.org/python-measure-time-taken-by-program-to-execute/)

本文旨在展示如何测量程序执行所花费的时间。计算时间有助于优化您的 Python 脚本以获得更好的性能。

**方法#1 :**
一个简单的解决方法是使用**时间**模块获取当前时间。以下步骤计算程序或程序部分的运行时间。

*   存储程序第一行执行前的开始时间。
*   存储程序最后一行执行后的结束时间。
*   打印开始时间和结束时间之间的差异。

**代码#1 :**

```py
# Code to Measure time taken by program to execute.
import time

# store starting time
begin = time.time()

# program body starts

for i in range(5):
    print("GeeksForGeeks")
# program body ends

time.sleep(1)
# store end time
end = time.time()

# total time taken
print(f"Total runtime of the program is {end - begin}")
```

**Output:**

```py
GeeksForGeeks
GeeksForGeeks
GeeksForGeeks
GeeksForGeeks
GeeksForGeeks
Total runtime of the program is 1.0010437965393066

```

**方法 2 :** 使用`Timeit`模块

```py
# importing the required module 
import timeit 

# code snippet to be executed only once 
mysetup = "from math import sqrt"

# code snippet whose execution time is to be measured 
mycode = ''' 
def example(): 
    mylist = [] 
    for x in range(100): 
        mylist.append(sqrt(x)) 
'''

# timeit statement 
print timeit.timeit(setup = mysetup, 
                    stmt = mycode, 
                    number = 10000) 
```

**输出:**

```py
0.00119590759277
```

**注意:**输出可能因系统或服务器负载而异。

要了解更多关于 Timeit 模块的信息，请参考 Python 中的–[time it 示例](https://www.geeksforgeeks.org/timeit-python-examples/)