# Python PIL | getbands()和 getextrema()方法

> 原文:[https://www . geesforgeks . org/python-pil-get bands-and-get extrema-method/](https://www.geeksforgeeks.org/python-pil-getbands-and-getextrema-method/)

Python PIL 库包含图像模块，其中定义了各种函数。 **PIL。此方法用于获取图像中出现的[模式](https://pillow.readthedocs.io/en/3.0.x/handbook/concepts.html#concept-modes)(乐队)。** 

> **语法:** PIL。image . image . getbands(image_object[有效图像路径])
> **参数:**
> 它取一个参数 image _ object，即它是使用 open()方法打开的图像的引用，也可以提到图像路径。
> **返回值:**返回包含该图像中每个波段名称的元组。例如，RGB 图像上的 getbands 返回(“R”、“G”、“B”)。

## 蟒蛇 3

```
# Importing Image module from PIL package
from PIL import Image

# Opening a multiband image
im = Image.open(r"C:\Users\Admin\Pictures\images.png")

# This returns the bands used in im (image)
im1 = Image.Image.getbands(im)

print("Multiband image", im1)

# Opening a single band image
im2 = Image.open(r"C:\Users\Admin\Pictures\singleband.png")

# This returns the band used in im2
im3 = Image.Image.getbands(im2)

print("Single band image", im3)
```

**输出:**

```
Multiband image ('R', 'G', 'B')
Single band image ('P', )
```

#### 国内生产总值。image . image . getextrema()方法-

获取图像中每个波段的最小和最大像素值。

> **语法:** PIL。image . image . getextrema(image_object[有效图像路径])
> **参数:**
> 它取一个参数 image _ object 即它是使用 open()方法打开的图像的引用，也可以提到图像路径。
> **返回值:**对于单波段图像，包含最小和最大像素值的二元组。对于多波段图像，每个波段包含一个 2 元组的元组。

## 蟒蛇 3

```
# importing Image module from PIL package
from  PIL import Image

# opening a multiband image
im = Image.open(r"C:\Users\Admin\Pictures\download.png")

# getting maximum and minimum pixels of
# multiband images (RBG)
im1 = Image.Image.getextrema(im)

print("Multi band image ", im1)

# Opening a single band image
im2 = Image.open(r"C:\Users\Admin\Pictures\singleband.png")

# getting maximum and minimum pixels of
# single band image
im3 = Image.Image.getextrema(im2)

print("Single band image ", im3)
```

**输出:**

```
Multi band image  ((73, 255), (0, 255), (0, 255))
Single band image  (0, 123)
```

**以上文章中使用的这些图像–**
**多波段图像**

![](img/1092edab31f80293476c292ae1155b47.png)

![](img/c3c72e1651b6c9e6d5daacace162fa95.png)

**单波段图像**

![](img/07ab1441a125adc25848dbac0593e73e.png)