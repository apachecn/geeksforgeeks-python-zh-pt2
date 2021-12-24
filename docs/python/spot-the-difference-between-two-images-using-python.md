# 使用 Python 找出两幅图像之间的差异

> 原文:[https://www . geesforgeks . org/spot-两个图像的区别-使用-python/](https://www.geeksforgeeks.org/spot-the-difference-between-two-images-using-python/)

在本文中，我们将讨论如何使用 python 发现两个给定图像之间的差异。为了执行这个任务，我们将使用*枕*模块中的*imagechops . difference()*方法。

> **语法:**T2【imagechops . difference(image1，image2)
> 
> ***参数:***
> 
> *   ***影像 1** 第一影像*
> *   ***图像 2** 第二个图像*
> 
> ***返回值:**返回一个图像。*

### 分步方法:

**第一步:**所以，今天我们将使用 python 构建这个神奇的工具，同样只用 8 行代码。但是，在此之前，我们必须使用这个命令安装 python 的枕头包

```
pip install pillow
```

**第二步:**现在，安装完这个之后，我们必须得到两个图像。确保这两个图像在您保存 python 程序的同一个文件夹中，否则您必须提供这些图像的路径。

**第三步:**以两幅图像为参数调用*imagechops . difference()*方法。

**步骤 4:** 使用 *show()* 方法生成两幅图像之间的差异。

### 实施:

**输入:**

![](img/26f9cc8cfd588613a3e686bfa4449767.png) ![](img/e7150eaa2b1fcbe56a27174d3cf6d9c9.png)

## 蟒蛇 3

```
# import module
from PIL import Image, ImageChops

# assign images
img1 = Image.open("1img.jpg")
img2 = Image.open("2img.jpg")

# finding difference
diff = ImageChops.difference(img1, img2)

# showing the difference
diff.show()
```

**输出:**

![](img/7e5ec23154c22d52b6ffca3690bacca5.png)

请注意，输出图像主要包含黑色部分，但该图像的某些部分是彩色的。这些彩色部分是两个输入图像之间的点状差异。在这种情况下，输出图像总共显示了 6 个主要差异。