# Python | time.get_clock_info()方法

> 原文:[https://www . geesforgeks . org/python-time-get _ clock _ info-method/](https://www.geeksforgeeks.org/python-time-get_clock_info-method/)

**Python 中的时间模块**提供了各种与时间相关的功能。

**时间模块**中的`***time.get_clock_info()***`方法用于获取指定时钟名称的信息。此方法将信息作为命名空间对象返回。
支持的时钟名称和读取该时钟值的方法如下:

*   时钟:`***time.clock()***`
*   单调:`***time.monotonic()***`
*   perf_counter : `***time.perf_counter()***`
*   process_time : `***time.process_time()***`
*   thread_time : `***time.thread_time()***`
*   时间:`***time.time()***`

> **语法:** time.get_clock_info(名称)
> 
> **参数:**
> **名称:**代表时钟名称的字符串值。
> 
> **返回类型:**该方法返回一个命名空间对象，该对象的属性表示指定时钟名称的信息。
> 以下是名称空间对象的属性:
> 
> *   **可调:**如果系统管理员可以自动或手动更改时钟，则此为“真”。否则为“假”。
> *   **实现:**用于获取时钟值的底层 C 函数的名称。
> *   **单调:**它的值是真的，如果时钟不能倒退的话。否则为假。
> *   **分辨率:**该属性以秒为单位指定时钟的分辨率。

**代码:**使用`***time.get_clock_info()***`方法

```py
# Python program to explain time.get_clock_info() method

# importing time module
import time

# Clock name
clock_name = 'clock'

# Get the information on
# the specified clock name
clock_info = time.get_clock_info(clock_name)

# Print the information
print("Information on '% s':" % clock_name)
print(clock_info) 

clock_name = 'perf_counter'

# Get the information on
# the specified clock name
clock_info = time.get_clock_info(clock_name)

# Print the information
print("\nInformation on '% s':" % clock_name)
print(clock_info) 

clock_name = 'process_time'

# Get the information on
# the specified clock name
clock_info = time.get_clock_info(clock_name)

# Print the information
print("\nInformation on '% s':" % clock_name)
print(clock_info) 
```

**Output:**

```py
Information on 'clock':
namespace(adjustable=False, implementation='clock()',
monotonic=True, resolution=1e-06)

Information on 'perf_counter':
namespace(adjustable=False, implementation='clock_gettime(CLOCK_MONOTONIC)',
monotonic=True, resolution=1e-09)

Information on 'process_time':
namespace(adjustable=False, implementation='clock_gettime(CLOCK_PROCESS_CPUTIME_ID)',
monotonic=True, resolution=1e-09)

```

**参考:**[https://docs . python . org/3/library/time . html # time . get _ clock _ info](https://docs.python.org/3/library/time.html#time.get_clock_info)