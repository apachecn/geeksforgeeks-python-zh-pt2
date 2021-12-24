# Python PIL | Image.frombuffer()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-from buffer-method/](https://www.geeksforgeeks.org/python-pil-image-frombuffer-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**PIL.Image.frombuffer()**`创建引用字节缓冲区中像素数据的图像存储器。

请注意，该函数仅解码像素数据，而不是整个图像。如果您有一个字符串形式的完整图像文件，请将其包装在一个 BytesIO 对象中，并使用 open()加载它。

> **语法:** PIL。Image.frombuffer(模式、大小、数据、decoder_name='raw '，*args)
> 
> **参数:**
> **模式**–图像模式。参见:模式
> **尺寸**–图像尺寸。
> **数据**–包含给定模式原始数据的字节缓冲区。
> **解码器 _ 名称**–使用什么解码器。
> **参数**–给定解码器的附加参数。对于默认编码器(“raw”)，建议您提供全套参数:`frombuffer(mode, size, data, "raw", mode, 0, 1)`
> 
> **返回:**一个图像对象。

**所用图像:**
![](img/830a03c07a38a5d0da94ca5826ef56d7.png)

```py

# importing image object from PIL
from PIL import Image

# creating an image object
im = Image.open(r"C:\Users\System-Pc\Desktop\rose.jpg")
im1 = im.tobytes("xbm", "rgb")
img = Image.frombuffer("L", (4, 4), im1, 'raw', "L", 0, 1)

# creating list 
img2 = list(img.getdata())
print(img2)
```

**输出:**

> [48, 120, 102, 102, 44, 48, 120, 102, 102, 44, 48, 120, 102, 102, 44, 48]

**另一个例子:**这里我们使用另一个图像。

**所用图像:**
![](img/9cbf1a9c1e25eca7ca32921c80e7f1bc.png)

```py

# importing image object from PIL
from PIL import Image

# creating an image object
im = Image.open(r"C:\Users\System-Pc\Desktop\ellipse1.png")
im1 = im.tobytes("xbm", "rgb")
img = Image.frombuffer("L", (10, 10), im1, 'raw', "L", 0, 1)

# creating list 
img2 = list(img.getdata())
print(img2)
```

**输出:**

> [48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 10, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56, 44, 48, 120, 56, 56]