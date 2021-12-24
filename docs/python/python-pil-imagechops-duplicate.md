# Python PIL | imagechops . duplicate()

> 原文:[https://www . geesforgeks . org/python-pil-image chops-replicate/](https://www.geeksforgeeks.org/python-pil-imagechops-duplicate/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **ImageChops.duplicate()** 包含许多算术图像操作，称为通道操作(“Chops”)。这些可以用于各种目的，包括特效、图像合成、算法绘画等等。

`**PIL.ImageChops.duplicate()**`复制一个频道。`PIL.Image.Image.copy()`的别名。复制()只是复制/复制图像。

> **语法:** PIL。ImageChops.duplicate(图像)
> 
> **参数:**
> **图像 1**–图像。
> 
> **返回类型:**一个图像。

**所用图像:**
![](img/a1ef8fe2abdd82fd82dcb35534ff789b.png)

```
## Importing Image and ImageChops module from PIL package 
from PIL import Image, ImageChops 

# creating a image1 object 
im1 = Image.open(r"C:\Users\System-Pc\Desktop\leave.jpg") 

# applying duplicate method 
im3 = ImageChops.duplicate(im1) 

im3.show() 
```

**输出:**

![](img/b3f8138561944dddd49d7c5039c0998d.png)