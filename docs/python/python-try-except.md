# Python 尝试除了

> 原文:[https://www.geeksforgeeks.org/python-try-except/](https://www.geeksforgeeks.org/python-try-except/)

Python 中的错误有两种类型，即语法错误和异常。错误是程序中的问题，由于这些问题，程序将停止执行。另一方面，当一些改变程序正常流程的内部事件发生时，就会引发异常。
**注:**更多信息，请参考 Python 中的[错误和异常](https://www.geeksforgeeks.org/errors-and-exceptions-in-python/?ref=lbp)
**一些常见的异常错误有:**

*   **IOError:** 如果文件无法打开
*   **键盘中断:**当用户按下不需要的键时
*   **值错误:**当内置函数接收到错误的参数时
*   **EOFError:** 如果在没有读取任何数据的情况下命中文件结束
*   **如果找不到模块，导入错误:**

## 试试除了 Python

Try and Except 语句用于处理 Python 代码中的这些错误。try 块用于检查一些代码是否有错误，即当程序中没有错误时，try 块中的代码将执行。然而，只要程序在前面的 try 块中遇到错误，except 块中的代码就会执行。

**语法:**

```py
try:
    # Some Code
except:
    # Executed if error in the
    # try block
```

**try()是如何工作的？**

*   首先执行 **try** 子句，即 **try** 和**之间的代码，除了**子句。
*   如果没有异常，那么只有**尝试**子句运行，**除外**子句结束。
*   如果出现任何异常，将跳过 **try** 子句，并运行**除外**子句。
*   如果出现任何异常，但是代码中除之外的**子句没有处理它，它将被传递到外部的 **try** 语句。如果未处理异常，则执行停止。**
*   一个**尝试**语句可以有多个**除了**子句

**代码 1:** 无异常，因此**尝试**子句将运行。

## 计算机编程语言

```py
# Python code to illustrate
# working of try()
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional Part as Answer
        result = x // y
        print("Yeah ! Your answer is :", result)
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")

# Look at parameters and note the working of Program
divide(3, 2)
```

**输出:**

```py
('Yeah ! Your answer is :', 1)
```

**代码 1:** 有一个例外，所以只有**除外**子句将运行。

## 计算机编程语言

```py
# Python code to illustrate
# working of try()
def divide(x, y):
    try:
        # Floor Division : Gives only Fractional Part as Answer
        result = x // y
        print("Yeah ! Your answer is :", result)
    except ZeroDivisionError:
        print("Sorry ! You are dividing by zero ")

# Look at parameters and note the working of Program
divide(3, 0)
```

**输出:**

```py
Sorry ! You are dividing by zero
```

### 否则条款

在 python 中，您还可以在 try-except 块上使用 else 子句，该子句必须出现在所有 except 子句之后。只有当 try 子句没有引发异常时，代码才会进入 else 块。

**语法:**

```py
try:
    # Some Code
except:
    # Executed if error in the
    # try block
else:
    # execute if no exception
```

**代码:**

## 蟒蛇 3

```py
# Program to depict else clause with try-except

# Function which returns a/b
def AbyB(a , b):
    try:
        c = ((a+b) / (a-b))
    except ZeroDivisionError:
        print "a/b result in 0"
    else:
        print c

# Driver program to test above function
AbyB(2.0, 3.0)
AbyB(3.0, 3.0)
```

**输出:**

```py
-5.0
a/b result in 0
```

### Python 中的 Finally 关键字

Python 最后提供了一个关键字，它总是在 try 和 except 块之后执行。由于某些异常，最终块总是在正常终止 try 块之后或 try 块终止之后执行。

**语法:**

```py
try:
    # Some Code
except:
    # Executed if error in the
    # try block
else:
    # execute if no exception
finally:
    # Some code .....(always executed)
```

**代码:**

## 蟒蛇 3

```py
# Python program to demonstrate finally

# No exception Exception raised in try block
try:
    k = 5//0 # raises divide by zero exception.
    print(k)

# handles zerodivision exception    
except ZeroDivisionError:   
    print("Can't divide by zero")

finally:
    # this block is always executed 
    # regardless of exception generation.
    print('This is always executed') 
```

**输出:**

```py
Can't divide by zero
This is always executed
```

**相关文章:**

*   [输出问题](https://www.geeksforgeeks.org/output-of-python-programs-set-10-exception-handling/)
*   [Python 中的异常处理](https://www.geeksforgeeks.org/python-set-5-exception-handling/)
*   [用户定义的异常](https://www.geeksforgeeks.org/user-defined-exceptions-python-examples/)

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。