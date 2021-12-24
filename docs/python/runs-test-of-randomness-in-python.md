# 在 Python 中运行随机性测试

> 原文:[https://www . geesforgeks . org/runs-测试 python 中的随机性/](https://www.geeksforgeeks.org/runs-test-of-randomness-in-python/)

随机数是许多系统中必不可少的一部分，包括模拟、密码学等等。因此，随机产生值的能力，没有明显的逻辑和可预测性，成为一个主要功能。因为计算机不能产生完全随机的值，所以被称为**伪随机数发生器(PRNG)** 的算法被用来完成这个任务。

PRNGs 产生的值并不是真正随机的，它取决于提供给算法的初始值，即种子值。给定伪随机序列的种子值，伪随机序列的可再现性对于其在模拟中的应用是至关重要的，例如蒙特卡罗模拟，其中系统可能需要在同一序列上测试不止一次。

**一些最受欢迎和使用率最高的 PRNGs 是:**

1.  **Mersenne Twister:** 用作 Python、R、Excel、Matlab、Ruby 等很多比较流行的软件系统中的默认随机数生成器。
2.  **线性同余生成器:**用于 C++和 Java
3.  **威奇曼-希尔生成器:**在 Excel 中使用，是 Python 2.2 中的默认值
4.  **帕克-米勒发电机**
5.  **中间方韦伊尔序列**

为了确保 PRNG 生成的值尽可能接近随机，使用了几个统计测试，包括 Diehard 测试、TestU01 系列、卡方测试和随机性的 Runs 测试。本文主要关注随机性的运行测试。

## 什么是运行测试？

运行随机性测试 是一个统计测试，用于检查数据的随机性。这是一种非参数检验，使用数据的游程来决定呈现的数据是随机的还是倾向于遵循某种模式。运行被定义为一系列递增值或递减值。数值增加或减少的数量就是游程的长度。

runs 测试的第一步是统计数据序列中的运行次数。有几种方法来定义运行，但是，在所有情况下，公式必须产生一个二分的值序列。在我们的案例中，高于中位数的值被视为正值，低于中位数的值被视为负值。运行被定义为一系列连续的正值或负值。

### 应用运行测试

*   应用该测试的第一步是制定零假设和替代假设。

**H <sub>null</sub> :** 序列是随机产生的

**H <sub>alt</sub> :** 序列不是随机产生的

*   计算测试统计，Z 为:

```py

Where, 
R = The number of observed runs
R' = The number of expected runs, given as

S<sub>R</sub> = Standard Deviation of the number of runs

With n1 and n2 = the number of positive and 
negative values in the series
```

*   将计算出的 Z 统计值与给定置信水平的 Z <sub>临界</sub>进行比较(对于 95%的置信水平，Z <sub>临界</sub> =1.96)。如果|Z| > Z <sub>临界</sub>，则否定零假设，即宣布数字不是随机的。

**例:**

## 蟒蛇 3

```py
# simple code to implement Runs 
# test of randomnes

import random
import math
import statistics

def runsTest(l, l_median):

    runs, n1, n2 = 0, 0, 0

    # Checking for start of new run
    for i in range(len(l)):

        # no. of runs
        if (l[i] >= l_median and l[i-1] < l_median) or \
                (l[i] < l_median and l[i-1] >= l_median):
            runs += 1  

        # no. of positive values
        if(l[i]) >= l_median:
            n1 += 1   

        # no. of negative values
        else:
            n2 += 1   

    runs_exp = ((2*n1*n2)/(n1+n2))+1
    stan_dev = math.sqrt((2*n1*n2*(2*n1*n2-n1-n2))/ \
                       (((n1+n2)**2)*(n1+n2-1)))

    z = (runs-runs_exp)/stan_dev

    return z

# Making a list of 100 random numbers 
l = []
for i in range(100):
    l.append(random.random())

l_median= statistics.median(l)

Z = abs(runsTest(l, l_median))

print('Z-statistic= ', Z)
```

**输出:**

```py
Z-statistic=  1.809160364503323
```