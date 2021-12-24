# Python 集| pop()

> 原文:[https://www.geeksforgeeks.org/python-set-pop/](https://www.geeksforgeeks.org/python-set-pop/)

Python 的这个内置功能有助于**从集合中弹出元素**，就像在实现 Stack 时概念中使用的原理一样。此方法**从集合中移除顶部元素**，但不移除随机元素，并返回移除的元素。

我们可以在使用 pop()方法之前通过打印集合来验证这一点。

**语法:**

```
# Pops a First element from S
# and returns it.
S.pop()
```

这是集合的基本功能之一，不接受任何参数。返回值是从集合中弹出的元素。一旦元素从集合中弹出，集合就会丢失该元素，并被更新为没有该元素的集合。

**示例:**

```
Input : 
sets = {1, 2, 3, 4, 5}
Output : 
1
Updated set is {2, 3, 4, 5}

Input : 
sets = {"ram", "rahim", "ajay", "rishav", "aakash"}
Output :
rahim
Updated set is {'ram', 'rishav', 'ajay', 'aakash'}
```

## 蟒蛇 3

```
# Python code to illustrate pop() method

S = {"ram", "rahim", "ajay", "rishav", "aakash"}

# Print the set before using pop() method
# First element after printing the set will be popped out
print(S)

# Popping three elements and printing them
print(S.pop())
print(S.pop())
print(S.pop())

# The updated set
print("Updated set is", S)
```

**输出:**

```
rishav
ram
rahim
Updated set is {'aakash', 'ajay'}
```

另一方面，如果设置为空，则返回**类型错误**，如以下程序所示。

## 蟒蛇 3

```
# Python code to illustrate pop() method
# on an empty set
S = {}

# Popping three elements and printing them
print(S.pop())

# The updated set
print("Updated set is", S)
```

**错误:**

```
Traceback (most recent call last):
  File "/home/7c5b1d5728eb9aa0e63b1d70ee5c410e.py", line 6, in 
    print(S.pop())
TypeError: pop expected at least 1 arguments, got 0
```