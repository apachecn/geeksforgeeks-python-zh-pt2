# Python PIL | Image.merge()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-merge-method/](https://www.geeksforgeeks.org/python-pil-image-merge-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.merge()**`将一组单波段图像合并成新的多波段图像。

> **语法:** PIL。Image.merge(模式，波段)
> 
> **参数:**
> 
> **模式**–用于输出图像的模式。请参阅:模式。
> **波段**–输出图像中每个波段包含一个单波段图像的序列。所有的乐队必须有相同的大小。
> 
> **返回:**一个图像对象。

**所用图像:**
![](img/b9d9345df71fc8e6c101def0e1afd214.png)

```

# importing Image class from PIL package 
from PIL import Image 

# creating a object 
image = Image.open(r"C:\Users\System-Pc\Desktop\home.png")
image.load()
r, g, b, a = image.split()

# merge funstion used
im1 = Image.merge( 'RGB', (r, g, b))
im1.show()
```

**输出:**
![](img/19b3c0139b6138f2b179df0507a4e55f.png)

**另一个例子:**这里用了另一个图像。

**所用图像:**
![](img/b676bf4e5579500345ba1e2db94e0f29.png)

```

# importing Image class from PIL package 
from PIL import Image 

# creating a object 
image = Image.open(r"C:\Users\System-Pc\Desktop\python.png")
image.load()
r, g, b, a = image.split()[1]

# merge funstion used
im1 = Image.merge('RGB', (r, g, b))
im1.show()
```

**输出:**
![](img/b2107747e4176f47c782d014223fef4d.png)