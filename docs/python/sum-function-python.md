# Python 中的 sum()函数

> 原文:[https://www.geeksforgeeks.org/sum-function-python/](https://www.geeksforgeeks.org/sum-function-python/)

列表中的数字总和在任何地方都是必需的。Python 提供了一个内置函数 sum()，它将列表中的数字相加。
 **语法:**

```
sum(iterable, start) 
iterable : iterable can be anything list , tuples or dictionaries ,
 but most importantly it should be numbers.
start : this start is added to the sum of 
numbers in the iterable. 
If start is not given in the syntax , it is assumed to be 0.
```

**可能的两种语法:**

```
sum(a)
a is the list , it adds up all the numbers in the 
list a and takes start to be 0, so returning 
only the sum of the numbers in the list.
sum(a, start)
this returns the sum of the list + start 

```

下面是 sum()的 Python 实现

```
# Python code to demonstrate the working of 
# sum()

numbers = [1,2,3,4,5,1,4,5]

# start parameter is not provided
Sum = sum(numbers)
print(Sum)

# start = 10
Sum = sum(numbers, 10)
print(Sum)
```

输出:

```
25
35

```

**错误和异常**

**类型错误:**当列表中除了数字之外还有其他内容时，会出现此错误。

```
# Python code to demonstrate the exception of 
# sum()
arr = ["a"]

# start parameter is not provided
Sum = sum(arr)
print(Sum)

# start = 10
Sum = sum(arr, 10)
print(Sum)
```

运行时错误:

```
Traceback (most recent call last):
  File "/home/23f0f6c9e022aa96d6c560a7eb4cf387.py", line 6, in 
    Sum = sum(arr)
TypeError: unsupported operand type(s) for +: 'int' and 'str'

```

**所以列表应该包含数字**

**实际应用:**需要计算和才能做进一步运算的问题，如求数的平均值。

```
# Python code to demonstrate the practical application
# of sum()

numbers = [1,2,3,4,5,1,4,5]

# start = 10
Sum = sum(numbers)
average= Sum/len(numbers) 
print (average)
```

输出:

```
3

```