# Python PIL | Image .转置()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-transpose-method/](https://www.geeksforgeeks.org/python-pil-image-transpose-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。图像模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。
**Image .转置()**转置图像(以 90 度步进翻转或旋转)

> **语法:**转置图像(以 90 度步进翻转或旋转)
> **参数** :
> **方法–PIL 之一。图像。翻转 _ 左 _ 右，PIL。图像。翻转 _ 顶部 _ 底部，PIL。图像。旋转 90 度，PIL。图像。旋转 180 度，PIL。返回类型:图像对象。**

**使用的图像:**

![](img/2547bf95d42fc2a3204dfdb8c100b664.png)

## 蟒蛇 3

```
# Importing Image class from PIL module
from PIL import Image

# Opens a image in RGB mode
im = Image.open(r"C:\Users\System-Pc\Desktop\new.jpg")

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
im1 = im1.transpose(Image.FLIP_LEFT_RIGHT)
# Shows the image in image viewer
im1.show()
```

**输出:**

![](img/ccc424c250a264568162876fe8b1fdda.png)

**另一个例子:这里变换参数被改变。**
**图像使用**

![](img/ac4ac741684b44b80bd3d781b17e109e.png)

## 蟒蛇 3

```
# Importing Image class from PIL module
from PIL import Image

# Opens a image in RGB mode
im = Image.open(r"C:\Users\System-Pc\Desktop\flower1.jpg")

# Size of the image in pixels (size of original image)
# (This is not mandatory)
width, height = im.size

# Setting the points for cropped image
left = 3
top = height / 2
right = 164
bottom = 3 * height / 2

# Cropped image of above dimension
# (It will not change original image)
im1 = im.crop((left, top, right, bottom))
newsize = (1800, 1800)
im1 = im1.transpose(Image.FLIP_TOP_BOTTOM)
# Shows the image in image viewer
im1.show()
```

**输出:**

![](img/317394abb3809e3fcf1a8bc526899c89.png)