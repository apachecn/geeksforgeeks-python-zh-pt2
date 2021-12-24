# Python PIL | imagechops . multiply()方法

> 原文:[https://www . geesforgeks . org/python-pil-image chops-multiple-method/](https://www.geeksforgeeks.org/python-pil-imagechops-multiply-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. The **ImageChops module** contains a number of arithmetical image operations, called channel operations (“chops”). These can be used for various purposes, including special effects, image compositions, algorithmic painting, and more.

**PIL。ImageChops.multiply()** 方法将两幅图像叠加在一起。
如果将一个图像乘以一个纯黑色图像，结果是黑色。如果与纯白色图像相乘，图像不受影响。至少有一个图像必须具有模式“1”。

```py
Syntax: PIL.ImageChops.multiply(image1, image2)

Parameters:
image1: first image
image2: second image

Return Type: Image

```

图片 1:
![](img/ef8daf8e2a485f9b7037151469c5affd.png)

图片 2:
![](img/f0a3c29a3d2f68702e80b19a25e320d7.png)

```py
# Importing Image and ImageChops module from PIL package 
from PIL import Image, ImageChops

# creating a image1 object
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

# creating a image2 object
im2 = Image.open(r"C:\Users\sadow984\Desktop\c1.PNG")

# applying multiply method
im3 = ImageChops.multiply(im1, im2)

im3.show()
```

**输出:**
![](img/344eb526d5c8356797578b1c5260f28f.png)

图片 3:
![](img/bfecff4b179a2833ca2629d92f01bb09.png)

图片 4:
![](img/0c8810d960c49d8e476e101d6cc1a77a.png)

```py
# Importing Image and ImageChops module from PIL package 
from PIL import Image, ImageChops

# creating a image3 object
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG")

# creating a image4 object
im2 = Image.open(r"C:\Users\sadow984\Desktop\a3.PNG")

# applying multiply method
im3 = ImageChops.multiply(im1, im2)

im3.show()
```

**输出:**
![](img/e025a4a1236f619718fa6d9768be804f.png)