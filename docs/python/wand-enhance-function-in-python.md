# Python 中的魔杖增强()功能

> 原文:[https://www . geesforgeks . org/wand-enhance-function-in-python/](https://www.geeksforgeeks.org/wand-enhance-function-in-python/)

与 despeckle()函数类似，该函数也降低了图像的噪声。**增强()**功能通过应用自动滤波器返回具有降低噪声的图像。

> **语法:** wand.image.enhance()
> 
> **参数:**增强()功能中没有参数

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    # reduce noise image using enhance() function
    img.enhance()
    img.save(filename ="vkoala.jpeg")
```

**输出:**
![](img/0baba1a1f01e1cbceabe25ecf3c789ac.png)

**例 2:**

**来源影像:**
![](img/ae742f3382017f51b1353cff13603d77.png)

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="road.jpeg") as img:
    # vignette image using vignette() function
    img.enhance()
    img.save(filename ="vkoala2.jpeg")
```

**输出:**
![](img/ae742f3382017f51b1353cff13603d77.png)