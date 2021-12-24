# Python |调用或定义函数时的范围解析

> 原文:[https://www . geesforgeks . org/python-scope-resolution-当调用或定义函数时/](https://www.geeksforgeeks.org/python-scope-resolution-when-a-function-is-called-or-defined/)

Python 以两种方式解析函数参数的范围:

*   当函数被定义时
*   当函数被调用时

**定义函数时**
考虑这个样本程序，它有一个函数加法器(a，b)，将一个元素 a 加到列表 b 上，返回列表 b，b 的默认值是[1，8，11]。
 **代码:**

```py
def adder(a, b = [1, 8, 11]):
    b.append(a)
    return b

print(adder(1))
print(adder(2))
print(adder(9))
print(adder(2, [3, 6]))
```

```py
Expected Output : 

[1, 8, 11, 1]
[1, 8, 11, 2]
[1, 8, 11, 9]
[3, 6, 2]

```

```py
Actual Output : 

[1, 8, 11, 1]
[1, 8, 11, 1, 2]
[1, 8, 11, 1, 2, 9]
[3, 6, 2]

```

请注意，即使我们在第二次和第三次调用中没有传递参数，默认值 b 也不再保留[1，8，11]。这是因为 **Python 只在函数定义时解析一次对函数范围内默认参数名称的引用，而不是每次调用它。**即使 a 和 b 是任何其他可变类型，如*字典和设置*，程序也会以同样的方式工作。
如果我们希望 b 的默认值总是[1，8，11]，我们该怎么办？在函数内部，我们可以检查调用函数时是否传递了 b。如果不是，那么我们把 b 的值重新分配给[1，8，11]。

**当函数被调用时**
现在，考虑这个程序**尝试**将 lambda 函数对象(计算 0 到 4 之间数字的平方)存储在一个列表中，并逐个调用它们。
**代码:**

```py
l = []
for i in range(5):
    l.append(lambda : i**2)
for j in range(5):
    print(l[j]())
```

```py
Expected Output : 

0
1
4
9
16

```

```py
Actual Output : 

16
16
16
16
16

```

然而，结果并不像计划中所预期的那样。这是因为 ***Python 在调用函数时而不是在定义函数时解析对函数范围内非默认参数名称的引用。*T3 这里的参数是 *i* 。当循环终止时， *i* 的值为 4，当我们调用 l 中存储的任何 lambda 函数时，返回 4**2 = 16。
我们如何让程序按照我们预期的方式运行？只需将 *i* 设为 lambda 函数的默认参数，并让 python 的范围解析行为为您实现。**