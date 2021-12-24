# Python 中的魔杖翻牌()功能

> 原文:[https://www.geeksforgeeks.org/wand-flop-function-in-python/](https://www.geeksforgeeks.org/wand-flop-function-in-python/)

在本文中，我们将学习什么是 flip()函数。基本上，这个函数返回一个翻转的图像。**翻转**效果将图像上下翻转或创建图像的垂直反射。这个函数不需要参数。

> **语法:**wand . image . flip()
> T3】参数:flip()函数中没有参数。

**例 1:**
**源图像:**

![](img/a1d5dabac07efe8de363e0c440a198d8.png)

## 蟒蛇 3

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:

    with img.clone() as fimg:
        # flopped image using flop() function
        fimg.flop()
        fimg.save(filename ='koalaflopped.jpeg')
```

**输出:**

![](img/7631c9187f74a8aaf04b4658634ae5e7.png)

**例 2:**
**来源影像:**

![](img/0dead08cbf71dacb9fdc290c1df11845.png)

## 蟒蛇 3

```py
from wand.image import Image

# Read image using Image function
with Image(filename ="man.jpeg") as img:
    with img.clone() as fimg:
        # flopped image using flop() function
        fimg.flop()
        fimg.save(filename ='manflopped.jpeg')
```

**输出:**

![](img/65296eb47b17a3e82ba1fe72e231f6ef.png)