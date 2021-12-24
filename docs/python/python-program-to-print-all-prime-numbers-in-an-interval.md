# Python 程序打印一个区间内的所有素数

> 原文:[https://www . geesforgeks . org/python-program-to-print-all-质数-in-interval/](https://www.geeksforgeeks.org/python-program-to-print-all-prime-numbers-in-an-interval/)

给定两个正整数开始和结束。任务是编写一个 Python 程序来打印一个区间中的所有素数。

**定义:**素数是一个大于 1 的自然数，除了 1 和它本身之外，没有任何正整数。前几个素数是{2，3，5，7，11，…}.

解决这个问题的思路是使用 for 循环对从*开始*到*结束*的*值*进行迭代，对于每个数字，如果大于 1，检查它是否除以 *n* 。如果我们找到任何其他除数，打印该值。

**下面是 Python 实现:**

## Python 3

```py
# Python program to print all
# prime number in an interval
# number should be greater than 1
start = 11
end = 25

for i in range(start, end+1):
    if i > 1:
        for j in range(2, i):
            if(i % j == 0):
                break
        else:
            print(i)
```

**输出:**

```py
11
13
17
19
23
```

上述解决方案可以使用厄拉多塞的[筛进行优化。详情请参见](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)[打印一个范围内的质数](https://www.geeksforgeeks.org/print-prime-numbers-given-range-using-c-stl/)。