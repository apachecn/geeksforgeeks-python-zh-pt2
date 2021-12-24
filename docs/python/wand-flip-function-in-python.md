# Python 中的魔杖翻转()功能

> 原文:[https://www.geeksforgeeks.org/wand-flip-function-in-python/](https://www.geeksforgeeks.org/wand-flip-function-in-python/)

在本文中，我们将学习什么是 flip()函数。基本上，这个函数返回一个翻转的图像。**翻转**效果将图像上下翻转或创建图像的垂直反射。这个函数不需要参数。

> **语法:**wand . image . flip()
> T3】参数:flip()函数中没有参数。

**来源图片:**

![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

## 蟒蛇 3

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    with img.clone() as fimg:
        # flip image using flip() function
        fimg.flip()
        fimg.save(filename ='koalaflipped.jpeg')
```

**输出:**

![](img/3a26a8d23108ebe40b6b77d384aa605f.png)

**例 2:**
**来源影像:**

![](img/0dead08cbf71dacb9fdc290c1df11845.png)

## 蟒蛇 3

```py
from wand.image import Image

# Read image using Image function
with Image(filename ="man.jpeg") as img:
    with img.clone() as fimg:
        # flip image using flip() function
        fimg.flip()
        fimg.save(filename ='manflipped.jpeg')
```

**输出:**

![](img/a67ea4bd23671036fb020f3bfc9ba20a.png)