# Python 中的尝试、除、否则和最后

> 原文:[https://www . geesforgeks . org/try-except-else-and-final-in-python/](https://www.geeksforgeeks.org/try-except-else-and-finally-in-python/)

异常是在程序执行过程中发生的事件。也称为**运行时间错误**。当错误发生时，Python 会在执行过程中生成一个可以处理的异常，从而避免程序中断。

**例:**

## 蟒 3

```
a = 5
b = 0
print(a/b)
```

**输出:**

```
Traceback (most recent call last):
  File "/home/8a10be6ca075391a8b174e0987a3e7f5.py", line 3, in <module>
    print(a/b)
ZeroDivisionError: division by zero
```

在这段代码中，系统不能将数字除以零，因此会引发异常。

## 用 try、except、else 和 finally 处理异常

*   **尝试**:该模块将测试异常错误是否发生
*   **除了**:这里可以处理错误
*   **否则**:如果没有异常，则执行该块
*   **最后**:无论是否生成异常，最终块总是被执行

**语法:**

```
try:
       # Some Code.... 

except:
       # optional block
       # Handling of exception (if required)

else:
       # execute if no exception

finally:
      # Some code .....(always executed)
```

我们先来了解一下 try and except 是如何工作的–

*   Execute **try** clause first, that is, the code between **try** clause and **except** clause.
*   If there is no exception, then only **try** clause will run, except **clause** will not be executed.
*   If there is an exception, the **try** clause will be skipped and the clause except **will be run.**
*   If an exception occurs, but **in the code is not handled except the** clause, it is passed to the external **try** statement. If the exception is not handled, execution stops.
*   A **try** statement can have multiple **clauses except** .

**示例:**让我们尝试接受用户整数输入，并在 except 块中抛出异常。

## 蟒 3

```
# Python code to illustrate
# working of try() 
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional
        # Part as Answer
        result = x // y
        print("Yeah ! Your answer is :", result)
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")

# Look at parameters and note the working of Program
divide(3, 2)
divide(3, 0)
```

**输出:**

```
Yeah ! Your answer is : 1
Sorry ! You are dividing by zero 
```

### 否则条款

只有当 try 子句没有引发异常时，代码才会进入 else 块。

**示例:**否则只有在没有异常发生时才会执行**。**

 **## 蟒 3

```
# Python code to illustrate
# working of try() 
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional
        # Part as Answer
        result = x // y
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")
    else:
        print("Yeah ! Your answer is :", result)

# Look at parameters and note the working of Program
divide(3, 2)
divide(3, 0)
```** 

**输出:**

```
Yeah ! Your answer is : 1
Sorry ! You are dividing by zero
```

### 最后关键词

Python 最后提供了一个关键字，就是**总是在尝试和除块之后执行**。finally 块总是在 try 块正常终止之后或者在 try 块由于某种异常而终止之后执行。

**示例:**让我们尝试将异常抛出异常块，最后将执行异常生成与否

## python 3

```
# Python code to illustrate
# working of try() 
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional
        # Part as Answer
        result = x // y
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")
    else:
        print("Yeah ! Your answer is :", result)
    finally: 
        # this block is always executed  
        # regardless of exception generation. 
        print('This is always executed')  

# Look at parameters and note the working of Program
divide(3, 2)
divide(3, 0)
```

**输出:**

```
Yeah ! Your answer is : 1
This is always executed
Sorry ! You are dividing by zero 
This is always executed
```