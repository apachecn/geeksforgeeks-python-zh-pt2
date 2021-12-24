# Python PIL | image . alpha _ composite()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-alpha _ composite-method/](https://www.geeksforgeeks.org/python-pil-image-alpha_composite-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.alpha_composite()**`α复合 im2 超过 im1。

> **语法:** PIL。Image.alpha_composite(im1，im2)
> 
> **参数:**
> **img 1**–第一张图片。
> **img 2**–第二张图片。必须具有与第一个图像相同的模式和大小。
> 
> **返回:**一个图像对象。

**Img1 使用:**
![](img/b9d9345df71fc8e6c101def0e1afd214.png)

**Img2 使用:**
![](img/686ce0abe8be10b924d2c483da582a22.png)

```

# importing image class from PIL package
from PIL import Image

# creating image object
img1 = Image.open(r"C:\Users\System-Pc\Desktop\home.png")

# creating image2 object having alpha
img2 = Image.open(r"C:\Users\System-Pc\Desktop\python.png")
img2 = img2.resize(img1.size)

# using alpha_composite
im3 = Image.alpha_composite(img1, img2)
im3.show()
```

**输出:**
![](img/f7f5dd57f1fdb1b3340344fc73f41676.png)