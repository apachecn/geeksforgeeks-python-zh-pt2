# Python PIL | Image.frombytes()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-from bytes-method/](https://www.geeksforgeeks.org/python-pil-image-frombytes-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**PIL.Image.frombytes()**`从缓冲区中的像素数据创建图像存储器的副本。在最简单的形式中，这个函数接受三个参数(模式、大小和未打包的像素数据)。

> **语法:** PIL。Image.frombytes(模式、大小、数据、decoder_name='raw '，*args)
> 
> **参数:**
> **模式**–影像模式。请参阅:模式。
> **尺寸**–图像尺寸。
> **数据**–包含给定模式原始数据的字节缓冲区。
> **解码器 _ 名称**–使用什么解码器。
> **参数**–给定解码器的附加参数。
> 
> **返回:**一个图像对象。

```

# importing image object from PIL
from PIL import Image

# using tobytes data as raw for frombyte function
tobytes = b'xd8\xe1\xb7\xeb\xa8\xe5 \xd2\xb7\xe1'
img = Image.frombytes("L", (3, 2), tobytes)

# creating list 
img1 = list(img.getdata())
print(img1)
```

**输出:**

```
[120, 100, 56, 225, 183, 235]

```

**另一个例子:**这里我们使用 tobytes 中不同的 raw。

```

# importing image object from PIL
from PIL import Image

# using tobytes data as raw for frombyte function
tobytes = b'\xbf\x8cd\xba\x7f\xe0\xf0\xb8t\xfe'
img = Image.frombytes("L", (3, 2), tobytes)

# creating list 
img1 = list(img.getdata())
print(img1)
```

**输出:**

```
[191, 140, 100, 186, 127, 224]

```