# Python PIL | tobytes()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-tobytes-method/](https://www.geeksforgeeks.org/python-pil-tobytes-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.tobytes()**`将图像作为字节对象返回

> **语法:**image . to bytes(encoder _ name = ' raw '，*args)
> 
> **参数:**
> 
> **编码器 _ 名称**–使用什么编码器。默认使用标准的“原始”编码器。
> **参数**–编码器的额外参数。
> 
> **返回:**一个字节对象。

**所用图像:**
![](img/dac0928016d419115c76c2872802a262.png)

```py

# Importing Image module from PIL package
from PIL import Image

# creating a image object
img = Image.open(r"C:\Users\System-Pc\Desktop\tree.jpg")

# using tobytes
img.tobytes("xbm", "rgb")
print(img)
```

**输出:**

```py
PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=259x194 at 0x2D39DED2BE0

```

**另一个例子:**这里使用相同的图像，编码器名称改为十六进制。

**所用图像:**
![](img/dac0928016d419115c76c2872802a262.png)

```py

# Importing Image module from PIL package
from PIL import Image

# creating a image object
img = Image.open(r"C:\Users\System-Pc\Desktop\tree.jpg")

# using tobytes
img.tobytes("hex", "rgb")
print(img)
```

**输出:**

```py
PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=259x194 at 0x27845B91BE0

```