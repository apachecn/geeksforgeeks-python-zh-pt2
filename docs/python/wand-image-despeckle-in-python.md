# Python 中的 Wand image.despeckle()

> 原文:[https://www . geesforgeks . org/wand-image-despeckle-in-python/](https://www.geeksforgeeks.org/wand-image-despeckle-in-python/)

**去斑效果**用于在不模糊边缘的情况下去除图像中的噪声。去毛刺滤波器平滑噪声明显的区域，不影响复杂区域。去斑点是可以用来减少给定图像上的噪声的许多技术之一。为了对图像执行去斑效果，使用了去斑()功能。

> **语法:**wand . image . despeckle()
> **参数:**无参数
> **返回:**返回图像

**示例#1:**
**使用的图像:**

![](img/f6e1f5e18898583c107a4cf1d5ed86c6.png)

## 蟒蛇 3

```py
# import Image from wand.image module
from wand.image import Image

with Image(filename ="koala.jpeg") as img:
    # perform despeckle effect
    img.despeckle()

    # save final image
    img.save(filename ="despeckle_koala.jpg")
```

**输出:**

![](img/4f699295783871bb0ebc425914269ddd.png)

**示例#2:**
**使用的图像:**

![](img/45f60a12341a7bca21d092de32e3c994.png)

## 蟒蛇 3

```py
# import Image from wand.image module
from wand.image import Image

with Image(filename ="frameman.jpeg") as img:
    # perform despeckle effect
    img.despeckle()

    # save final image
    img.save(filename ="despeckle_frameman.jpg")
```

**输出:**

![](img/d56c82879de1c4734344fb2d129df47c.png)