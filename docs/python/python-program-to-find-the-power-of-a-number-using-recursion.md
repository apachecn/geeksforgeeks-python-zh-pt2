# Python 程序利用递归求一个数的幂

> 原文:[https://www . geesforgeks . org/python-program-to-find-power-of-number-use-recursion/](https://www.geeksforgeeks.org/python-program-to-find-the-power-of-a-number-using-recursion/)

给定一个数 N 和幂 p，任务是编写一个 Python 程序，使用递归来求一个数的幂。

**定义:**一个数的幂可以定义为该数重复的次数乘以其幂的次数。

**示例:**

```
Input: N=2 , P=3
Output: 8

Input: N=5 , P=2
Output: 25

```

这个想法是计算一个数的幂“N”乘以这个数“P”，即在第一个例子中，N=2，P=3，我们通过三次重复乘以 2 得到结果，得到输出 8。

**下面是实现:**

## 蟒蛇

```
def power(N, P):

    # if power is 0 then return 1
    if P == 0:
        return 1

    # if power is 1 then number is
    # returned
    elif P == 1:
        return N

    else:
        return (N*power(N, P-1))

# Driver program
N = 5
P = 2

print(power(N, P))
```

**输出:**

```
25

```