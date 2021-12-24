# 为什么嵌套循环的执行速度比扁平循环快得多？

> 原文:[https://www . geeksforgeeks . org/为什么嵌套循环比扁平循环执行得快得多/](https://www.geeksforgeeks.org/why-does-a-nested-loop-perform-much-faster-than-the-flattened-one/)

Python 提供了三种执行循环的方法。虽然所有的方法都提供类似的基本功能，但是它们的语法和条件检查时间不同。

在本文中，我们将了解为什么嵌套循环比扁平循环性能更好。但是首先，让我们看看什么是嵌套循环，什么是扁平循环。

*   **Nested loop** is a logical structure in computer programming and coding. One of the loop statements is inside another loop statement.

**语法:**

```py
for [iter_1] in [sequence_1]:
    for [iter_2] in [sequence_2]:

          # statements of inner loop
          statements(iter_2)

    # statements of outer loop
    statements(iter_1)  
```

*   **循环**能够迭代任何序列的项目，如列表或字符串。

**语法:**

```py
for [iter] in sequence:
     statements(s)
```

当我们运行 python 脚本时，我们运行的操作系统会为它分配一个进程标识。它可以被系统调用中断，并且它的优先级可以随着时间而改变。但是，当我们更改内存地址或值时，系统不太可能从进程中拿走资源。当我们对循环进行平面运行时，它分配的变量比嵌套循环少得多。所以我们可以说，如果资源可用的话，嵌套循环比平面循环更能利用资源。

**例:**

## 蟒 3

```py
# import module
import time

# flattened loop
def loop(n):
    for i in range(n**3):
        pass

# nested loop
def nested(n):

    for i in range(n):
        for j in range(n):
            for k in range(n):
                pass

for i in range(10, 100, 10):
    start = time.time()
    loop(i)
    print('For flattened loop:',time.time() - start)

    start = time.time()
    nested(i)
    print('For nested loop:',time.time() - start)
    print()
```

**输出:**

```py
For flattened loop: 2.7894973754882812e-05
For nested loop: 4.9114227294921875e-05

For flattened loop: 0.0002155303955078125
For nested loop: 0.00024271011352539062

For flattened loop: 0.0007171630859375
For nested loop: 0.0007529258728027344

For flattened loop: 0.0016894340515136719
For nested loop: 0.0012614727020263672

For flattened loop: 0.0029077529907226562
For nested loop: 0.0022766590118408203

For flattened loop: 0.004510402679443359
For nested loop: 0.003597736358642578

For flattened loop: 0.007539272308349609
For nested loop: 0.0057599544525146484

For flattened loop: 0.01167440414428711
For nested loop: 0.008468151092529297

For flattened loop: 0.016645431518554688
For nested loop: 0.01381683349609375
```

我们可以看到，嵌套循环所花费的时间随着 n 值的增加而减少。