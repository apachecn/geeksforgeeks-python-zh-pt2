# Python 程序查找每个列表元素的立方体

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-cube-of-the-to-the-to-the-to-the-cube-of-of-list-element/](https://www.geeksforgeeks.org/python-program-to-find-the-cube-of-each-list-element/)

给定一个列表，任务是编写一个 python 程序来立方所有列表元素。

> **输入:**【1，2，3，4】
> 
> **输出**:【1，8，27，64】
> 
> **解释:**将所有列表元素立体化
> 
> **输入:**【2，4，6】
> 
> **输出:**【8，64，216】

**方法 1 :** *使用循环*

这是蛮力方式。在这种情况下，我们只需将同一个元素相乘两次。

**示例:**

## 蟒蛇 3

```py
# Initializing list
l = [1, 2, 3, 4]

# Cube List using loop
res = []
for i in l:
    res.append(i*i*i)

# printing result
print(res)
```

**输出:**

> [1, 8, 27, 64]

**方法二:** *使用 pow()函数*

这也是蛮力的方式。在这种情况下，我们使用内置的 [pow()](https://www.geeksforgeeks.org/pow-in-python/) 函数

**示例:**

## 蟒蛇 3

```py
# Initializing list
l = [1, 2, 3, 4]

# Cube List using loop
res = []
for i in l:
    res.append(pow(i, 3))

# printing result
print(res)
```

**输出:**

> [1, 8, 27, 64]

**方法三:** *使用列表理解*

这个任务也可以使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)来执行。这类似于上面的功能。只是不同的是它的紧凑型和一个内胆。

**例**:

## 蟒蛇 3

```py
# Initializing list
l = [1, 2, 3, 4]

# Cube List using list comprehension
res = [pow(i, 3) for i in l]

# printing result
print(res)
```

**输出:**

> [1, 8, 27, 64]

**方法 4:** *使用λ*

这也可以使用 lambda 函数来实现

**示例:**

## 蟒蛇 3

```py
# Initializing list
l = [1, 2, 3, 4]

res = list(map(lambda x: x ** 3, l))
print(res)
```

**输出:**

> [1, 8, 27, 64]