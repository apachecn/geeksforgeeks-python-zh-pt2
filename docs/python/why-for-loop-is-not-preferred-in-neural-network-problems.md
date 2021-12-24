# 为什么在神经网络问题中 For 循环不是首选？

> 原文:[https://www . geeksforgeeks . org/为什么神经网络中的循环不是首选问题/](https://www.geeksforgeeks.org/why-for-loop-is-not-preferred-in-neural-network-problems/)

[对于循环](https://www.geeksforgeeks.org/python-for-loops/)需要很多时间来完成迭代，在 ML 练习中，我们必须优化时间，以便可以用于循环。但是你一定想知道用什么？别担心，我们将在下一节讨论这个问题。

### 如何摆脱机器学习或神经网络中的循环？

解决方案是矢量化。现在问题来了什么是矢量化？矢量化是将算法从一次对单个值进行运算转换为一次对一组值(向量)进行运算的过程。现代中央处理器为向量运算提供直接支持，其中一条指令应用于多个数据(SIMD)。

### 为什么循环使用矢量化？

矢量化用于加快 Python 代码的速度。使用 np.function 有助于有效地最小化代码的运行时间。让我们看看下面的例子，以便更好地理解。

**示例:**

```py
import numpy as np
import time

a = np.array([1, 2, 3, 4])

# there will be 100000 training data
a = np.random.rand(100000)
b = np.random.rand(100000)

# FOR VECTORIZTION
# Measure current time
time1 = time.time()

# computing
c = np.dot(a, b)

# Measure current time
time2 = time.time()

# printing time taken for above calculation
print("vectorized form time taken"+ "\t"+str(1000*(time2-time1))+"ms")

# FOR for loop
# measure current time
time3 = time.time()
c = 0

# computing 
for i in range(100000):
  c+= a[i]*b[i]

# measure current time
time4 = time.time()

# printing time taken for above calculation
print("for loop time taken "+"\t\t"+str(1000*(time4-time3))+"ms")
```

**输出:**

```py
vectorized form time taken    0.43511390686035156ms
for loop time taken         216.04394912719727ms
```