# Python 中的系统最大化

> 原文:[https://www.geeksforgeeks.org/sys-maxint-in-python/](https://www.geeksforgeeks.org/sys-maxint-in-python/)

在编程中， **maxint/INT_MAX** 表示可以用整数表示的最高值。在某些情况下，在编程时，我们可能需要分配一个比任何其他整数值都大的值。通常情况下，需要手动分配这些值。例如，考虑一个整数列表，其中必须使用循环的**找到最小值。**

## 计算机编程语言

```py
# initializing the list
li = [1, -22, 43, 89, 2, 6, 3, 16]

# assigning a larger value manually
curr_min = 999999

# loop to find minimum value
for i in range(0, len(li)):

    # update curr_min if a value lesser than it is found
    if li[i] < curr_min:
        curr_min = li[i]

print("The minimum value is " + str(curr_min))
```

**Output**

```py
The minimum value is -22

```

在上面的方法中，我们假设 **999999** 是我们列表中最大的可能值，并将其与其他元素进行比较，以便在找到小于它的值时进行更新。

### Python 中的 sys 模块

该模块用于与解释器交互，并访问解释器维护的变量。它可以用来在运行时环境中执行操作。这必须像其他包一样导入才能利用其中的功能。Python 的 **sys 模块**提供了多种函数和常量，其中常量 **maxint** ，可以用来设置一个正整数值，保证大于任何其他整数。请看下面的例子。

## 计算机编程语言

```py
# import the module
import sys

# initializing the list
li = [1, -22, 43, 89, 2, 6, 3, 16]

# assigning a larger value with 
# maxint constant
curr_min = sys.maxint

# loop to find minimum value
for i in range(0, len(li)):

    # update curr_min if a value lesser 
    # than it is found
    if li[i] < curr_min:
        curr_min = li[i]

print("The minimum value is " + str(curr_min))
```

**Output**

```py
The minimum value is -22

```

在上面的程序中，使用 **sys.maxint** 代替手动分配更大的值。Python 版支持该常数。该常数表示的值可以计算如下:

> maxint = 2<sup>31</sup>–1(在 32 位环境中)
> 
> maxint = 2<sup>63</sup>–1(在 64 位环境中)

在 **Python 2** 中，最大值加 1 得到最大可能值 **long int** ，在 **Python 2.7** 中，最大值减 1 得到整数的最小可能值。

## 计算机编程语言

```py
# import the module
import sys

max_int = sys.maxint
min_int = sys.maxint-1
long_int = sys.maxint+1

print("maxint :"+str(max_int)+" - "+str(type(max_int)))
print("maxint - 1 :"+str(max_int)+" - "+str(type(min_int)))
print("maxint + 1 :"+str(max_int)+" - "+str(type(long_int)))
```

**Output**

```py
maxint :9223372036854775807 - <type 'int'>
maxint - 1 :9223372036854775807 - <type 'int'>
maxint + 1 :9223372036854775807 - <type 'long'>

```

该常数从 Python 3 中删除，因为该版本中的整数被认为是任意长度的。如果您在 Python 3 中使用这个常量，那么您将会得到以下错误。考虑相同的例子，其中最小值元素必须从列表中找到。

## 蟒蛇 3

```py
import sys

# initializing the list
li = [1, -22, 43, 89, 2, 6, 3, 16]

# assigning a larger value with maxint constant
curr_min = sys.maxint

# loop to find minimum value
for i in range(0, len(li)):

    # update curr_min if a value lesser than it is found
    if li[i] < curr_min:
        curr_min = li[i]

print("The minimum value is " + str(curr_min))
```

**输出:**

```py
AttributeError: module 'sys' has no attribute 'maxint'

```

由于对整数的值不再有限制，因此删除了该常数。在 **Python 3 中，**引入了一个与此类似的常量，即 **sys.maxsize** 。这将返回变量类型 **Py_ssize_t** 的最大可能整数值，同时也表示平台的指针大小。这个 maxsize 被认为限制了各种数据结构的大小，比如字符串和列表。另一件需要注意的事情是，在 Python 3 中 **int** 和 **long int** 合二为一。为了更好的理解，请看下面的例子。

## 蟒蛇 3

```py
# import the module
import sys

# using sys.maxsize
max_int = sys.maxsize
min_int = sys.maxsize-1
long_int = sys.maxsize+1

print("maxint :"+str(max_int)+" - "+str(type(max_int)))
print("maxint - 1 :"+str(max_int)+" - "+str(type(min_int)))

# the data type is represented as int
print("maxint + 1 :"+str(max_int)+" - "+str(type(long_int)))
```

**Output**

```py
maxint :9223372036854775807 - <class 'int'>
maxint - 1 :9223372036854775807 - <class 'int'>
maxint + 1 :9223372036854775807 - <class 'int'>

```