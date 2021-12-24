# Python |一个数的超级工厂。

> 原文:[https://www . geesforgeks . org/python-super factory-of-a-number/](https://www.geeksforgeeks.org/python-superfactorial-of-a-number/)

给定一个数，任务是找到一个数的超级工厂。前 n 个阶乘的乘积相乘的结果称为一个数的**超因子**。

```
Superfactorial(n)= 1 ^ n * 2 ^ (n-1) * 3 ^ (n-2) * . . . . . * n ^ 1
```

**示例:**

> **输入:**3
> T3】输出: 12
> H(3) = 1！* 2!* 3!= 12
> 
> **输入:** 4
> **输出:**288
> h(4)= 1^4 * 2^3 * 3^2 * 4^1 = 288

一种有效的方法是迭代计算所有阶乘直到 n，然后计算所有阶乘的乘积直到 n。

```
# Python3 program to find the
# Superfactorial of a number

# function to calculate the
# value of Superfactorial 
def superfactorial(n):

    # initialise the
    # val to 1
    val = 1
    ans = []
    for i in range(1, n + 1):
        val = val * i
        ans.append(val)
    # ans is the list with
    # all factorial till n.
    arr = [1]
    for i in range(1, len(ans)):
        arr.append((arr[-1]*ans[i]))

    return arr

# Driver Code
n = 5
arr = superfactorial(n)
print(arr[-1])
```

**Output:**

```
34560

```

**时间复杂度:** O(N)
由于数的超阶乘可能很大，因此数会溢出。我们可以用 C++中的 [boost 库](https://www.geeksforgeeks.org/advanced-c-boost-library/)或者 Java 中的[big integer](https://www.geeksforgeeks.org/biginteger-class-in-java/)来存储一个数 n 的超阶乘。