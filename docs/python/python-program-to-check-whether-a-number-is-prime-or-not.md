# Python 程序检查一个数字是否是质数

> 原文:[https://www . geesforgeks . org/python-program-to-check-number-is-prime-or-not/](https://www.geeksforgeeks.org/python-program-to-check-whether-a-number-is-prime-or-not/)

给定一个正整数 N，任务是写一个 Python 程序来检查这个数是否是[素数](https://www.geeksforgeeks.org/prime-numbers/)。
**定义:**素数是一个大于 1 的自然数，除了 1 和它本身之外，没有其他正整数。前几个素数是{2，3，5，7，11，…}.

**示例:**

> **输入:**n = 11
> T3】输出:真
> 
> **输入:**n = 15
> T3】输出:假
> 
> **输入:**n = 1
> T3】输出:假

解决这个问题的想法是使用 for 循环遍历从 2 到(N/2)的所有数字，并检查每个数字是否除以 N。如果我们找到任何除以的数字，我们返回 false。如果我们没有找到 2 和 N/2 之间的任何数来除 N，那么这意味着 N 是素数，我们将返回真。

下面是检查一个数字是否是质数的 Python 程序:

## 蟒蛇 3

```py
# Python program to check if
# given number is prime or not

num = 11

# If given number is greater than 1
if num > 1:

    # Iterate from 2 to n / 2
    for i in range(2, int(num/2)+1):

        # If num is divisible by any number between
        # 2 and n / 2, it is not prime
        if (num % i) == 0:
            print(num, "is not a prime number")
            break
    else:
        print(num, "is a prime number")

else:
    print(num, "is not a prime number")
```

**Output**

```py
11 is a prime number
```

**优化方法**
我们可以做以下优化:

我们可以检查到√n，而不是检查到 n，因为 n 的较大因子必须是已经检查过的较小因子的倍数。

现在让我们看看第一个优化方法的代码(即检查到√n)

## 蟒蛇 3

```py
from math import sqrt
# n is the number to be check whether it is prime or not
n = 1

# no lets check from 2 to sqrt(n)
# if we found any facto then we can print as not a prime number

# this flag maintains status whether the n is prime or not
prime_flag = 0

if(n > 1):
    for i in range(2, int(sqrt(n)) + 1):
        if (n % i == 0):
            prime_flag = 1
            break
    if (prime_flag == 0):
        print("true")
    else:
        print("false")
else:
    print("false")
```

**Output**

```py
false
```

通过观察除了 2 和 3 之外，所有素数都是 6k ^ 1 形式，可以进一步改进算法。这是因为对于某些整数 k 和对于 i = -1、0、1、2、3 或 4，所有整数都可以表示为(6k+I)；2 除(6k + 0)，(6k + 2)，(6k+4)；和 3 除(6k + 3)。所以更有效的方法是测试 n 是否能被 2 或 3 整除，然后检查 6k ^ 1 形式的所有数字。(来源:[维基百科](https://en.wikipedia.org/wiki/Primality_test))