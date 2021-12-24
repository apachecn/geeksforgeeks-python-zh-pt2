# Python PIL | imageops . postarize()方法

> 原文:[https://www . geesforgeks . org/python-pil-imageops-post arize-method/](https://www.geeksforgeeks.org/python-pil-imageops-postarize-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **ImageOps 模块**包含多个‘现成’的图像处理操作。这个模块有些实验性，大多数操作人员只处理 L 和 RGB 图像。

`**ImageOps.posterize()**`减少每个颜色通道的位数。在每一个比特的变化中，都会看到颜色收缩的变化

> **语法:** PIL。ImageOps.posterize(图像)
> 
> **参数** :
> **图像**–用于后期处理的图像。
> **位**–每个通道要保留的位数(1-8)。位 8 是通道可以使用的最大位。
> 
> **返回:**一个图像。

**所用图像:**
![](img/535e4d950fe7c6fc28f5fad49114bccc.png)

```py
# Importing Image and ImageOps module from PIL package 
from PIL import Image, ImageOps 

# creating a image1 object 
im1 = Image.open(r"C:\Users\System-Pc\Desktop\a.JPG") 

# applying posterize method 
im2 = ImageOps.posterize(im1, 2) 

im2.show()
```

**输出:**

![](img/99c98d363ef453a07188e127017feb51.png)

**位**–这里取位 4，通过改变通道中的位来了解颜色的变化。

```py
# Importing Image and ImageOps module from PIL package 
from PIL import Image, ImageOps 

# creating a image1 object 
im1 = Image.open(r"C:\Users\System-Pc\Desktop\a.JPG") 

# applying posterize method 
im2 = ImageOps.posterize(im1, 4) 

im2.show()
```

**输出:**

![](img/da78a031a28f4f3bb0e76c3eb1170dbc.png)