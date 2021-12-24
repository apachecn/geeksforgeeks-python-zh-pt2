# Python PIL | imageops . equal()方法

> 原文:[https://www . geesforgeks . org/python-pil-imageops-equal-method/](https://www.geeksforgeeks.org/python-pil-imageops-equalize-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. the **ImageOps module** contains a number of ‘ready-made’ image processing operations. This module is somewhat experimental, and most operators only work on L and RGB images.`**ImageOps.equalize()**` method equalizes the image histogram. This function applies a non-linear mapping to the input image, in order to create a uniform distribution of grayscale values in the output image.

> **语法:** PIL。图像操作.均衡(图像，遮罩=无)
> 
> **参数:**
> **图像:**将图像进行均衡。
> **面具:**可选面具。如果给定，则分析中仅包括由遮罩选择的像素。
> 
> **返回:**一个图像。

所用图像:
![](img/345594dbc341bc7b8ffa447ae3bc2a4f.png)

```py
# Importing Image and ImageOps module from PIL package  
from PIL import Image, ImageOps 

# creating a image1 object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\download2.JPg")

# applying equalize method 
im2 = ImageOps.equalize(im1, mask = None)

im2.show() 
```

**输出:**
![](img/d318465a01303c6c440fa6ef3bff33bf.png)