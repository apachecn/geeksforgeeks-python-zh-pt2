# Python PIL | ImageChops .核减()方法

> 原文:[https://www . geesforgeks . org/python-pil-image chops-减法-method/](https://www.geeksforgeeks.org/python-pil-imagechops-subtract-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. The **ImageChops module** contains a number of arithmetical image operations, called channel operations (“chops”). These can be used for various purposes, including special effects, image compositions, algorithmic painting, and more.

`**PIL.ImageChops.subtract()**`方法减去两幅图像，将结果除以比例，再加上偏移量。如果省略，比例默认为 1.0，偏移默认为 0.0。至少有一个图像必须具有模式“1”。

```py
Syntax: PIL.ImageChops.subtract(image1, image2, scale=1.0, offset=0)

Parameters:
image1: first image
image2: second image
scale: numeric value
offset: numeric value

Return Type: Image

```

图片 1:
![](img/4d1bd5c364d9eec579f058fc615f2263.png)

图片 2:
![](img/6cee4d89707d2caba1b2fcf8a0f8b8c9.png)

```py
# Importing Image and ImageChops module from PIL package  
from PIL import Image, ImageChops 

# creating a image1 object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG") 

# creating a image2 object 
im2 = Image.open(r"C:\Users\sadow984\Desktop\x5.PNG") 

# applying subtract method 
im3 = ImageChops.add(im1, im2, scale = 1.0, offset = 2) 

im3.show() 
```

**输出:**
![](img/da8086c2c66faaa839da99ca52369008.png)

```py
# Importing Image and ImageChops module from PIL package  
from PIL import Image, ImageChops 

# creating a image1 object 
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG") 

# creating a image2 object 
im2 = Image.open(r"C:\Users\sadow984\Desktop\x5.PNG") 

# applying subtract method 
im3 = ImageChops.add(im1, im2, scale = 1.0, offset = 2) 

im3.show() 
```

**输出:**
![](img/0a69d41e08ce33c51745519739503326.png)