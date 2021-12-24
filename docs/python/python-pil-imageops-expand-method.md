# Python PIL | ImageOps.expand()方法

> 原文:[https://www . geesforgeks . org/python-pil-imageops-expand-method/](https://www.geeksforgeeks.org/python-pil-imageops-expand-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。**图像操作模块**包含许多“现成的”图像处理操作。这个模块有些实验性，大多数操作人员只处理 L 和 RGB 图像。
**ImageOps.expand()** 为调用或使用此函数的图像添加边框。

> **语法** : PIL。ImageOps.expand(image，border = 0，fill = 0)
> **参数** :
> **图像:**将图像进行尺寸和裁剪。
> **边框:**应用于图像的边框，单位为像素。
> **填充:**定义要应用的像素填充值或颜色值。默认值为 **0** ，表示颜色为**黑色**。
> **返回**:带有所需边框的图像。

下面是**imageops . expand()**
**的实现图片使用:**

![](img/20a4d1ac78f5191971152bf8af260f6a.png)

## 蟒蛇 3

```py
# Importing Image and ImageOps module from PIL package
from PIL import Image, ImageOps

# creating a image1 object
im1 = Image.open(r"C:\Users\System-Pc\Desktop\a.jpg")

# applying expand method
# using border value = 20
# using fill = 50 which is brown type color
im2 = ImageOps.expand(im1, border = 20, fill = 50)

im2.show()
```

**输出:**

![](img/4e730d8be802fbca9594fdd7422be62d.png)