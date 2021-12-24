# Python 程序最多三个

> 原文:[https://www.geeksforgeeks.org/python-program-maximum-three/](https://www.geeksforgeeks.org/python-program-maximum-three/)

给定三个数字 a、b 和 c，任务是我们必须在给定的数字中找到最大的元素
例子:

```
Input : a = 2, b = 4, c = 3
Output : 4 

Input : a = 4, b = 2, c = 6 
Output : 6

```

**方法 1(简单)**

```
# Python program to find the largest
# number among the three numbers

def maximum(a, b, c):

    if (a >= b) and (a >= c):
        largest = a

    elif (b >= a) and (b >= c):
        largest = b
    else:
        largest = c

    return largest

# Driven code 
a = 10
b = 14
c = 12
print(maximum(a, b, c))
```

输出:

```
14

```

**方法 2(使用列表)**
**。**通过 n1、n2 和 n3
**初始化三个数字。**在列表 lst = [n1，n2，n3]中添加三个数字。
**。**利用 max()函数求最大数 max(lst)。
**。**最后我们将打印最大数量

```
# Python program to find the largest number 
# among the  three numbers using library function 

def maximum(a, b, c):
    list = [a, b, c]
    return max(list)

# Driven code 
a = 10
b = 14
c = 12
print(maximum(a, b, c))
```

输出:

```
14

```

**方法 3(使用最大功能)**

```
# Python program to find the largest number 
# among the  three numbers using library function 

# Driven code 
a = 10
b = 14
c = 12
print(max(a, b, c))
```

输出:

```
14

```