# Python PIL | imagechops . light()方法

> 原文:[https://www . geesforgeks . org/python-pil-image chops-light-method/](https://www.geeksforgeeks.org/python-pil-imagechops-lighter-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. The ImageChops module contains a number of arithmetical image operations, called channel operations (“chops”). These can be used for various purposes, including special effects, image compositions, algorithmic painting, and more.`**PIL.ImageChops.lighter()**` method compares the two images, pixel by pixel, and returns a new image containing the lighter values. At least one of the images must have mode “1”.

```py
Syntax: PIL.ImageChops.lighter(image1, image2)

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

# applying lighter method
im3 = ImageChops.lighter(im1, im2)

im3.show()
```

**输出:**
![](img/34a508ffc16eb2a58e6f107da6f35508.png)

```py
# Importing Image and ImageChops module from PIL package 
from PIL import Image, ImageChops

# creating a image1 object
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

# creating a image2 object
im2 = Image.open(r"C:\Users\sadow984\Desktop\c1.PNG")

# applying lighter method
im3 = ImageChops.lighter(im2, im1)

im3.show()
```

**输出:**【参数互换】
![](img/34a508ffc16eb2a58e6f107da6f35508.png)