# Python 中的 Wand 函数()函数

> 原文:[https://www . geesforgeks . org/wand-function-function-in-python/](https://www.geeksforgeeks.org/wand-function-function-in-python/)

**函数()**函数类似于求值函数。在**函数()**函数中，可以通过对像素通道应用多参数函数来操纵像素通道。
以下是魔杖中的函数类型列表:

*   '未定义'
*   "阿尔辛"
*   "北极"
*   多项式
*   正弦曲线

> **语法:**
> 
> ```py
> wand.image.function(function, arguments, channel)
> ```
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 功能 | 集合. abc .序列 | 应用于函数的一系列替身 |
> | 争论 | 数字。真实的 | 用运算符
> 计算的数字 |
> | 频道 | 基绳 | 对其应用操作的可选通道。
>  |
> 
> </figure>

**例 1:**
**来源影像:**

![](img/a1d5dabac07efe8de363e0c440a198d8.png)

## 蟒蛇 3

```py
# Import Image from wand.image module
from wand.image import Image

frequency = 3
phase_shift = -90
amplitude = 0.2
bias = 0.7

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # applying sinusoid FUCTION_TYPE
    img.function('sinusoid', [frequency, phase_shift, amplitude, bias])
    img.save(filename ="kl-functioned.jpeg")
```

**输出:**

![](img/1d3c534763a67d42a3d120cdf6cc3c35.png)

**例 2:**
**来源影像:**

![](img/d9a61cb82675859f69ca556aad95fbb7.png)

## 蟒蛇 3

```py
# Import Image from wand.image module
from wand.image import Image

frequency = 3
phase_shift = -90
amplitude = 0.2
bias = 0.7

# Read image using Image function
with Image(filename ="road.jpeg") as img:
    # applying sinusoid FUCTION_TYPE
    img.function('polynomial', [frequency, phase_shift, amplitude, bias])
    img.save(filename ="rd-functioned.jpeg")
```

**输出:**

![](img/04adcfa5c50286599bb251e3d2c658df.png)