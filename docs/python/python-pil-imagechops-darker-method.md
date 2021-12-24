# Python PIL | imagechops . darner()方法

> 原文:[https://www . geesforgeks . org/python-pil-image chops-darner-method/](https://www.geeksforgeeks.org/python-pil-imagechops-darker-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。

`ImageChops.darker()`方法用于逐像素比较两幅图像，并返回包含较暗值的新图像。

> **语法:**imagechops . dark(image1，image2)
> 
> **参数:**
> **image1:** 是第一幅图像的图像对象或图像路径。
> **image2:** 是第二张图像的图像对象或图像路径。
> 
> **返回值:**图像
> 
> **注意:**两幅图像应该是相同的**模式**。

**代码#1:**

```
# importing Image class from PIL package
from PIL import ImageChops, Image

# opening images to compare
im1 = Image.open(r"C:\Users\Admin\Pictures\download.png")
im2 = Image.open(r"C:\Users\Admin\Pictures\images.png")

# Checking and returning a copy
# of image contating darker pixels
im = ImageChops.darker(im1, im2)

# showing image
im.show()
```

**输出:**
![](img/41569315275908b6377e27ae643f11d4.png)

**代码#2:**

```
# importing Image class from PIL package
from PIL import ImageChops, Image

# opening images to compare
im1 = Image.open(r"C:\Users\Admin\Pictures\geeks.png")
im2 = Image.open(r"C:\Users\Admin\Pictures\capture.png")

# Checking and returning a copy
# of image contating darker pixels
im = ImageChops.darker(im1, im2)

# showing image
im.show()
```

**输出:**
![](img/9309f028f6e16d4394733bb7ac807fb1.png)

**注:**不要与`Image.blend()`法混淆。这种方法完全不同