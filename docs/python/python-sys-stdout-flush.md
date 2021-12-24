# Python–sys . stdout . flush()

> 原文:[https://www.geeksforgeeks.org/python-sys-stdout-flush/](https://www.geeksforgeeks.org/python-sys-stdout-flush/)

数据缓冲区是物理内存存储区域，用于在数据从一个地方移动到另一个地方时临时存储数据。当从输入设备检索数据时，或者在数据被发送到输出设备之前，或者在计算机内的进程之间移动数据时，数据被存储在缓冲区中。Python 的标准输出是缓冲的。这意味着，在写入标准输出之前，它会收集一些数据，当缓冲区填满时，它会写入终端或任何其他输出流。

让我们看看下面的代码:

```
# Python3 program demonstrating working 
# of flush during output  

import sys
import time

for i in range(10):
    print(i)
    time.sleep(1)
```

**输出:**

```
0
1
2
3
4
5
6
7
8
9
```

当执行上述程序时，从 0 到 9 的数字每秒钟都被打印在一个新行上，即输出被自动刷新。这是因为默认情况下打印语句的[结束参数设置为“\n”，这将刷新输出。](https://www.geeksforgeeks.org/gfact-50-python-end-parameter-in-print/)

现在让我们看看下面的代码:

```
# Python3 program demonstrating working 
# of flush during output

import sys
import time

for i in range(10):
    print(i, end =' ')
    time.sleep(1)
```

**输出:**

```
0 1 2 3 4 5 6 7 8 9
```

当执行上述程序时，前 9 秒没有输出，然后在第 10 个<sup>处，从 0 到 9 的所有 10 个数字同时出现在一行中，用空格隔开。这是因为输出是缓冲的，不会被任何方式刷新。</sup>

现在，看看下面的代码:

```
# Python3 program demonstrating working 
# of flush during output and usage of
# sys.stdout.flush() function

import sys
import time

for i in range(10):
    print(i, end =' ')
    sys.stdout.flush()
    time.sleep(1)
```

**输出:**

```
0 1 2 3 4 5 6 7 8 9
```

执行上述程序时，从 0 到 9 的数字每秒钟打印在由空格分隔的同一行上。这是因为调用`sys.stdout.flush()`会强制它“刷新”缓冲区，这意味着它会将缓冲区中的所有内容写入终端，即使正常情况下它会在这样做之前等待。sys 模块提供了用于操作 Python 运行时环境不同部分的函数和变量。它允许我们访问系统特定的参数和功能。

实现上述相同功能的另一种方法是将 print 语句的 flush 参数设置为 true。

```
# Python3 program demonstrating working 
# of flush during output and usage of
# flush parameter of print statement

import sys
import time

for i in range(10):
    print(i, end =' ', flush = True)
    time.sleep(1)
```

**输出:**

```
0 1 2 3 4 5 6 7 8 9 
```