# Python PIL | getpixel()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-getpixel-method/](https://www.geeksforgeeks.org/python-pil-getpixel-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。像素访问类提供对 PIL 的读写访问。像素级的图像数据。
访问单个像素相当慢。如果你正在循环一个图像中的所有像素，可能有一个更快的方法使用枕头应用编程接口的其他部分。
**getpixel()** 返回 x，y 位置的像素，该像素作为单个
返回

> **语法:** getpixel(self，xy)
> **参数:**
> **xy :** 像素坐标，给定为(x，y)。
> **返回:**单波段图像的像素值，多波段图像的像素值元组。

**使用的图像:**

![](img/ee1e3e82d42af5694c89c469a0f5a294.png)

## 蟒蛇 3

```py
# Importing Image from PIL package
from PIL import Image

# creating a image object
im = Image.open(r"C:\Users\System-Pc\Desktop\leave.jpg")
px = im.load()
print (px[4, 4])
px[4, 4] = (0, 0, 0)
print (px[4, 4])
coordinate = x, y = 150, 59

# using getpixel method
print (im.getpixel(coordinate));
```

**输出:**

```py
(130, 105, 49)
(0, 0, 0)
(75, 19, 0)
```

**另一个例子:**这里我们改变坐标值。
T3】使用的图像 T5】

![](img/ee1e3e82d42af5694c89c469a0f5a294.png)

## 蟒蛇 3

```py
# Importing Image from PIL package
from PIL import Image

# creating a image object
im = Image.open(r"C:\Users\System-Pc\Desktop\leave.jpg")
px = im.load()
print (px[4, 4])
px[4, 4] = (0, 0, 0)
print (px[4, 4])
coordinate = x, y = 180, 79

# using getpixel method
print (im.getpixel(coordinate));
```

**输出:**

```py
(130, 105, 49)
(0, 0, 0)
(22, 168, 25)
```