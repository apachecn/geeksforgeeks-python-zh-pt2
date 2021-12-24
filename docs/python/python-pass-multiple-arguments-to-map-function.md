# Python–将多个参数传递给映射函数

> 原文:[https://www . geesforgeks . org/python-pass-multi-arguments-to-map-function/](https://www.geeksforgeeks.org/python-pass-multiple-arguments-to-map-function/)

map()函数是 Python 中的一个内置函数，它将一个给定的函数应用于 iterable 的每一项(如 list、tuple 等)，并返回结果或 map 对象的列表。

> **语法:**
> 
> 贴图(funct、iterbl)
> 
> **参数:**
> 
> funct:要为每个可迭代对象执行的函数:要映射的可迭代对象的序列或集合

**注:**

1.  你可以通过任意多的可迭代来映射()函数。
2.  确保每个可迭代函数都有一个参数。

**示例:**

## 蟒蛇 3

```
# Python program to show working
# of map() function

# Return cube of n
def cube(n):
    return n**3

# Taking list as iterator
evennum = [2,4,6,8]
res = map(cube,evennum)
print(list(res))
```

**输出:**

```
[8, 64, 216, 512]

```

## **将多个参数传递给 map()函数**

我们可以将多个可迭代的参数传递给 map()函数。为此，必须遵守某些规则-

*   假设我们将 **n** 传递给 map()，那么给定的函数应该有 **n** 个参数。
*   这些可迭代参数必须并行应用于给定的函数。
*   在多个可迭代参数中，当最短可迭代被耗尽时，映射迭代器将停止。
*   但是在 Python 2 的情况下，当最长的序列结束时，映射迭代器将停止。

**代码 1 :** 传递两个列表和‘sum’函数映射()。

**进场:**

*   定义一个函数 sum，它返回两个数的和。
*   声明并初始化 ls1 和 ls2。
*   将 sum 函数 lst1 和 lst2 传递给 map()。
*   列表中索引 0 处的元素将作为参数传递给 sum 函数，并将返回它们的总和。
*   这个循环一直持续到一个列表的元素耗尽。
*   结果将存储在结果列表中。

## 蟒蛇 3

```
# Python program to demonstrate
# passing of multiple iterable arguments to map()
# using 2 lists

# Function which return sum of 2 numbers
def sum(a,b):
    return a+b

# list 1
lst1=[2,4,6,8]

# list 2
lst2=[1,3,5,7,9]

result=list(map(sum,lst1,lst2))
print(result)
```

**输出:**

```
[3, 7, 11, 15]

```

**代码 2 :** 通过三个列表和“乘法”函数映射()。

**进场:**

*   定义一个乘法函数，它返回三个数字的乘积。
*   声明并初始化 lst1、lst2 和 lst3。
*   将乘法函数 lst1、lst2 和 lst3 传递给 map()。
*   所有三个列表中索引 0 处的元素将作为参数传递给乘法函数，并将返回它们的乘积。
*   这个循环一直持续到一个列表的元素耗尽。
*   结果将存储在结果列表中。

## 蟒蛇 3

```
# Python program to demonstrate
# passing of multiple iterable arguments to map()
# using 3 lists

# Function which return product of 2 numbers
def Multiply(a,b,c):
    return a*b*c

# list 1
lst1=[2,4,6,8,10,12,14,16]

# list 2
lst2=[1,3,5,7,9,11,15]

#list 3
lst3=[2,3,5,7,11,13,17]

result=list(map(Multiply,lst1,lst2,lst3))
print(result)
```

**输出:**

```
[4, 36, 150, 392, 990, 1716, 3570]

```

**代码 3 :** 通过‘除法’函数，将一个列表和一个元组映射到()。

**进场:**

*   定义和初始化列表和元组。
*   定义执行两个数除法的除法函数。
*   将 lst、tup 和除法函数传递给 map()。
*   列表和元组中索引 0 处的元素将作为参数传递给除法函数，并将返回它们的商。
*   这个循环一直持续到列表或元组的元素耗尽。
*   结果将存储在结果列表中。

## 蟒蛇 3

```
# Python program to demonstrate
# passing of multiple iterable arguments to map()
# using list and tuple

# Function which perform division of 2 numbers
def division(a,b):
    return a/b

# list 
lst=[2,4,6,8,10,12,14,16]

# tuple
tup=(2,3,5,7,9,11)

result=list(map(division,lst,tup))
print(result)
```

**输出:**

> [1.0, 1.3333333333333333, 1.2, 1.1428571428571428, 1.1111111111111112, 1.0909090909090908]