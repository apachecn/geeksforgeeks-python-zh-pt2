# Python PIL | ImageOps.flip()方法

> 原文:[https://www . geesforgeks . org/python-pil-imageops-flip-method/](https://www.geeksforgeeks.org/python-pil-imageops-flip-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。**图像操作模块**包含许多“现成的”图像处理操作。这个模块有些实验性，大多数操作人员只处理 L 和 RGB 图像。

`**ImageOps.flip()**`垂直翻转图像(从上到下)。

> **语法:** PIL.ImageOps.flip(image)
> 
> **参数** :
> **图像**–要翻转的图像。图像将垂直翻转。
> 
> **返回**:图像。

**所用图像:**
![](img/3bc219b6226daf75802b3680c64417ac.png)

```py
# Importing Image and ImageOps module from PIL package 
from PIL import Image, ImageOps 

# creating a image1 object 
im1 = Image.open(r"C:\Users\System-Pc\Desktop\a.JPG") 

# applying flip method 
im2 = ImageOps.flip(im1) 

im2.show()
```

**输出:**

![](img/f92df68dc179acde8c05752bb5854235.png)