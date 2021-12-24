# Python PIL | Image.crop()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-image-crop-method/](https://www.geeksforgeeks.org/python-pil-image-crop-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。PIL。Image.crop()方法用于裁剪任何图像的矩形部分。

> **语法:** PIL。Image.crop(box = None)
> **参数:**
> **box–**定义左、上、右和下像素坐标的 4 元组。
> **返回类型:**图像(以(左、上、右、下)元组形式返回矩形区域)。
> **返回:**一个**图像**对象。

**代码#1:**

## 蟒蛇 3

```py
# Importing Image class from PIL module
from PIL import Image

# Opens a image in RGB mode
im = Image.open(r"C:\Users\Admin\Pictures\geeks.png")

# Size of the image in pixels (size of original image)
# (This is not mandatory)
width, height = im.size

# Setting the points for cropped image
left = 5
top = height / 4
right = 164
bottom = 3 * height / 4

# Cropped image of above dimension
# (It will not change original image)
im1 = im.crop((left, top, right, bottom))

# Shows the image in image viewer
im1.show()
```

**原图**

![](img/1986530ad3422a3e48f8d28d96bcb6b8.png)

**输出:**

![](img/de4df76ba1a88e00b55d95fad48439d3.png)

**代码#2:**

## 蟒蛇 3

```py
# Importing Image class from PIL module
from PIL import Image

# Opens a image in RGB mode
im = Image.open(r"C:\Users\Admin\Pictures\network.png")

# Setting the points for cropped image
left = 155
top = 65
right = 360
bottom = 270

# Cropped image of above dimension
# (It will not change original image)
im1 = im.crop((left, top, right, bottom))

# Shows the image in image viewer
im1.show()
```

**原图:**

![](img/0d9657ba992feb949a511fdc51494e03.png)

**输出:**

![](img/b5260bf793eed3ff0073f624b3846448.png)