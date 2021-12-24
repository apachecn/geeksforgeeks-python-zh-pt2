# Python |将列表中所有数字相乘(4 种不同方式)

> 原文:[https://www . geesforgeks . org/python-乘法-数字-列表-3-不同方式/](https://www.geeksforgeeks.org/python-multiply-numbers-list-3-different-ways/)

给定一个列表，打印列表中所有数字相乘后得到的值。
示例:

```
Input :  list1 = [1, 2, 3] 
Output : 6 
Explanation: 1*2*3=6 

Input : list1 = [3, 2, 4] 
Output : 24 

```

**方法 1:遍历**

将乘积的值初始化为 1(不是 0，因为 0 乘以任何值都会返回零)。遍历到列表的末尾，将每个数字乘以乘积。存储在产品最后的价值会给你最终的答案。
下面是上述方法的 Python 实现:

## 计算机编程语言

```
# Python program to multiply all values in the
# list using traversal

def multiplyList(myList) :

    # Multiply elements one by one
    result = 1
    for x in myList:
         result = result * x
    return result

# Driver code
list1 = [1, 2, 3]
list2 = [3, 2, 4]
print(multiplyList(list1))
print(multiplyList(list2))
```

**输出:**

```
6
24 

```

**方法二:使用 numpy.prod()**

我们可以从 import numpy 中使用 [numpy.prod()](https://www.geeksforgeeks.org/numpy-prod-python/) 得到列表中所有数字的乘积。它根据乘法结果返回一个整数或浮点值。
下面是上述方法的 Python3 实现:

## 蟒蛇 3

```
# Python3 program to multiply all values in the
# list using numpy.prod()

import numpy
list1 = [1, 2, 3]
list2 = [3, 2, 4]

# using numpy.prod() to get the multiplications
result1 = numpy.prod(list1)
result2 = numpy.prod(list2)
print(result1)
print(result2)
```

**输出:**

```
6
24 

```

**方法 3 使用 lambda 函数:使用 numpy.array**

Lambda 的定义不包括**“return”**语句，它总是包含一个被返回的表达式。我们还可以将 lambda 定义放在任何期望函数的地方，而且我们根本不需要将它赋给变量。这就是 lambda 函数的简单性。Python 中的 **reduce()** 函数接受一个函数和一个列表作为参数。使用 lambda 函数和列表调用该函数，并返回一个 n **ew 缩减结果**。这在列表对上执行重复操作。
下面是上述方法的 Python3 实现:

## 蟒蛇 3

```
# Python3 program to multiply all values in the
# list using lambda function and reduce()

from functools import reduce
list1 = [1, 2, 3]
list2 = [3, 2, 4]

result1 = reduce((lambda x, y: x * y), list1)
result2 = reduce((lambda x, y: x * y), list2)
print(result1)
print(result2)
```

**输出:**

```
6
24 

```

**方法 4 使用数学库的 prod 函数:使用 math.prod**

从 Python 3.8 开始，标准库中的数学模块中包含了一个 prod 函数，因此不需要安装外部库。
下面是上述方法的 Python3 实现:

## 蟒蛇 3

```
# Python3 program to multiply all values in the
# list using math.prod

import math
list1 = [1, 2, 3]
list2 = [3, 2, 4]

result1 = math.prod(list1)
result2 = math.prod(list2)
print(result1)
print(result2)
```

**输出:**

```
6
24 

```