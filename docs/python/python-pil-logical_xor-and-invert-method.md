# Python PIL | logic _ xor()和 invert()方法

> 原文:[https://www . geesforgeks . org/python-pil-logic _ xor-and-invert-method/](https://www.geeksforgeeks.org/python-pil-logical_xor-and-invert-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. The **ImageChops module** contains a number of arithmetical image operations, called channel operations (“chops”). These can be used for various purposes, including special effects, image compositions, algorithmic painting, and more.

`**PIL.ImageChops.logical_xor()**`方法对两幅图像进行逻辑异或运算。至少有一个图像必须具有模式“1”。

图片 1:
![](img/231c4e08af3581db4dc1a52b75b726d2.png)
图片 2:
![](img/0b8183d7169496f39249d9ad7eeec299.png)

> **语法:** PIL。imagechops . logic _ xor(image1，image2)
> 
> **参数:**
> **影像 1:** 第一影像
> **影像 2:** 第二影像
> 
> **返回类型:**图像

```
# Importing Image and ImageChops module from PIL package  
from PIL import Image, ImageChops 

# creating a image1 object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG") .convert("1")

# creating a image2 object 
im2 = Image.open(r"C:\Users\sadow984\Desktop\x5.PNG") .convert("1")

# applying logical_xor method 
im3 = ImageChops.logical_xor(im1, im2) 

im3.show() 
```

**输出:**
![](img/bf51c2e51550a1e7da57f8c9a4116d41.png)

`**PIL.ImageChops.invert()**`方法反转图像(通道)。

> **语法:** PIL。ImageChops.invert(图像)
> 
> **参数:**T2**影像 1:** 影像
> 
> **返回类型:**图像

```
# Importing Image and ImageChops module from PIL package  
from PIL import Image, ImageChops 

# creating a image1 object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG")

# applying invert method 
im3 = ImageChops.invert(im1) 

im3.show() 
```

**输出:**
![](img/535787fda1e0846826e1cfbd186511c4.png)