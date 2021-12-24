# Python PIL | Image.thumbnail()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-thumbnail-method/](https://www.geeksforgeeks.org/python-pil-image-thumbnail-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.thumbnail()**`将此图像制作成缩略图。此方法修改图像以包含其自身的缩略图版本，不大于给定的大小。此方法计算适当的缩略图大小以保留图像的外观，调用`draft()`方法配置文件读取器(如果适用)，最后调整图像的大小。

请注意，该函数会就地修改图像对象。如果您也需要使用全分辨率图像，请将此方法应用于原始图像的`copy()`。

> **语法:** Image.thumbnail(大小，重采样=3)
> 
> **参数:**
> **尺寸**–要求尺寸。
> **重采样**–可选重采样过滤器。
> 
> **返回类型:**一个图像对象。

**所用图像:**
![](img/b676bf4e5579500345ba1e2db94e0f29.png)

```

# importing Image class from PIL package 
from PIL import Image

# creating a object 
image = Image.open(r"C:\Users\System-Pc\Desktop\python.png")
MAX_SIZE = (100, 100)

image.thumbnail(MAX_SIZE)

# creating thumbnail
image.save('pythonthumb.png')
image.show()
```

**输出:**
![](img/a0ce511d599ca2cf9d78317eed8db696.png)

**另一个例子:**这里用了另一个图像。

**所用图像:**
![](img/f2bf49a278f52afa1751d7582edcd757.png)

```

# importing Image class from PIL package 
from PIL import Image

# creating a object 
image = Image.open(r"C:\Users\System-Pc\Desktop\house.jpg")
MAX_SIZE = (500, 500)

image.thumbnail(MAX_SIZE)

# creating thumbnail
image.save('pythonthumb2.jpg')
image.show()
```

**输出:**
![](img/60e599f57241289adfc6679cad59d180.png)