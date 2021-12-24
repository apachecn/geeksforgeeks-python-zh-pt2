# Python PIL | Image.point()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-point-method/](https://www.geeksforgeeks.org/python-pil-image-point-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.point()**`通过查找表或函数映射该图像。

> **语法:**通过查找表或函数映射此图像。
> 
> **参数:**
> 
> **lut**–一个查找表，包含图像中每个波段的 256 个(如果 self . mode = =“I”和 mode = =“L”)值。可以用一个函数来代替，它应该接受一个参数。对于每个可能的像素值，该函数被调用一次，结果表被应用于图像的所有波段。
> 
> **模式**–输出模式(默认与输入相同)。在当前版本中，只有当源图像具有模式“L”或“P”，并且输出具有模式“1”或源图像模式为“I”，并且输出模式为“L”时，才能使用此选项。
> 
> **返回:**一个图像对象。

**所用图像:**
![](img/b9d9345df71fc8e6c101def0e1afd214.png)

```py

# importing Image class from PIL package 
from PIL import Image 

# creating a object 
im = Image.open(r"C:\Users\System-Pc\Desktop\home.png") 

# using point function
threshold = 191  
im = im.point(lambda p: p >value threshold and 255)
im.show()
```

**输出:**
![](img/f631e864d56c51472ebeda539500dd05.png)

**另一个例子:**这里改变阈值。

**所用图像:**
![](img/a7d3e3c9f7a67c04fe1756deb3008ccc.png)

```py

# importing Image class from PIL package 
from PIL import Image 

# creating a object 
im = Image.open(r"C:\Users\System-Pc\Desktop\home.png") 

# using point function
threshold = 120  
im = im.point(lambda p: p > threshold and 255)
im.show()
```

**输出:**
![](img/a92b13d8d93b177484b3d7ac2322f4f0.png)