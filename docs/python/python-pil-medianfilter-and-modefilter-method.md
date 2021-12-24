# Python PIL | MedianFilter()和 ModeFilter()方法

> 原文:[https://www . geesforgeks . org/python-pil-median filter-and-modefilter-method/](https://www.geeksforgeeks.org/python-pil-medianfilter-and-modefilter-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. The ImageFilter module contains definitions for a pre-defined set of filters,which can be used with the `Image.filter()` method.

`**PIL.ImageFilter.MedianFilter()**`方法创建一个中值滤波器。在给定大小的窗口中选取中间像素值。

```py
Syntax: PIL.ImageFilter.MedianFilter(size=3)

Parameters:
size: The kernel size, in pixels.

```

所用图像:
![](img/c466c7906016e0a01d239d899551f011.png)

```py
# Importing Image and ImageFilter module from PIL package  
from PIL import Image, ImageFilter 

# creating a image object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\download2.JPG") 

# applying the median filter 
im2 = im1.filter(ImageFilter.MedianFilter(size = 3)) 

im2.show() 
```

**输出:**
![](img/7af76ce637c0ce07b0edb8ae8e220faa.png)

`**PIL.ImageFilter.ModeFilter()**`方法创建模式过滤器。选取给定大小的框中最常见的像素值。仅出现一次或两次的像素值将被忽略；如果没有像素值出现两次以上，则保留原始像素值。

```py
Syntax: PIL.ImageFilter.ModeFilter(size=3)

Parameters:
size: The kernel size, in pixels.

```

```py
# Importing Image and ImageFilter module from PIL package  
from PIL import Image, ImageFilter 

# creating a image object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\download2.JPG") 

# applying the mode filter 
im2 = im1.filter(ImageFilter.ModeFilter(size = 3)) 

im2.show() 
```

**输出:**
![](img/3cd1269938b53ba091128ae78aaf2f71.png)