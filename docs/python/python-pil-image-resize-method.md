# Python PIL | Image.resize()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-resize-method/](https://www.geeksforgeeks.org/python-pil-image-resize-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。图像模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。
**Image.resize()** 返回此图像的调整后的副本。

> **语法:** Image.resize(大小，重采样=0)
> **参数**:
> **size**–请求的像素大小，为二元组:(宽度，高度)。
> **重采样**–可选的重采样过滤器。这可能是 PIL 的一个。图片。最近的(使用最近的邻居)，PIL。图像。双线性(线性插值)，PIL。双三次样条插值，或 PIL。Image.LANCZOS(高质量下采样滤波器)。如果省略，或者图像有模式“1”或“P”，则设置为“PIL . Image . NEXTERAL .
> **返回类型**:图像对象。

**使用的图像:**

![](img/6e1a40517bd9f6bb62eeadef957096c7.png)

## 蟒蛇 3

```py
# Importing Image class from PIL module
from PIL import Image

# Opens a image in RGB mode
im = Image.open(r"C:\Users\System-Pc\Desktop\ybear.jpg")

# Size of the image in pixels (size of original image)
# (This is not mandatory)
width, height = im.size

# Setting the points for cropped image
left = 4
top = height / 5
right = 154
bottom = 3 * height / 5

# Cropped image of above dimension
# (It will not change original image)
im1 = im.crop((left, top, right, bottom))
newsize = (300, 300)
im1 = im1.resize(newsize)
# Shows the image in image viewer
im1.show()
```

**输出:**

![](img/581cf51c9f3344c7a68045d4a1b47efc.png)

**另一个例子:**这里我们使用了不同的 newsize 值。

## 蟒蛇 3

```py
# Importing Image class from PIL module
from PIL import Image

# Opens a image in RGB mode
im = Image.open(r"C:\Users\System-Pc\Desktop\ybear.jpg")

# Size of the image in pixels (size of original image)
# (This is not mandatory)
width, height = im.size

# Setting the points for cropped image
left = 6
top = height / 4
right = 174
bottom = 3 * height / 4

# Cropped image of above dimension
# (It will not change original image)
im1 = im.crop((left, top, right, bottom))
newsize = (200, 200)
im1 = im1.resize(newsize)
# Shows the image in image viewer
im1.show()
```

**输出:**

![](img/eff9779340a1f653837ce1ce098bcb65.png)