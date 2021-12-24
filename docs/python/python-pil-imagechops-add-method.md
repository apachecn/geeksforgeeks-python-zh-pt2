# Python PIL | ImageChops.add()方法

> 原文:[https://www . geesforgeks . org/python-pil-image chops-add-method/](https://www.geeksforgeeks.org/python-pil-imagechops-add-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. The **ImageChops module** contains a number of arithmetical image operations, called channel operations (“chops”). These can be used for various purposes, including special effects, image compositions, algorithmic painting, and more.`**PIL.ImageChops.add()**` method adds two images, dividing the result by scale and adding the offset. If omitted, scale defaults to 1.0, and offset to 0.0\. At least one of the images must have mode “1”. And scale and offset can have different values also.

```py
Syntax: PIL.ImageChops.add(image1, image2, scale=1.0, offset=0)

Parameters:
image1: first image
image2: second image
scale: numeric value
offset: numeric value

Return Type: Image

```

图片 1:
![](img/d9c532f8d6adef3ad5f6a16aad962781.png)

图片 2:
![](img/ea3e3299eac3d108d68bdaec86ee059e.png)

```py
# Importing Image and ImageChops module from PIL package 
from PIL import Image, ImageChops

# creating a image1 object
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG")

# creating a image2 object
im2 = Image.open(r"C:\Users\sadow984\Desktop\x5.PNG")

# applying add method
im3 = ImageChops.add(im1, im2, scale = 1.0, offset = 2)

im3.show()
```

**输出:**
![](img/3460f06f3f56290adc8e32a3ca587ae5.png)

```py
# Importing Image and ImageChops module from PIL package
from PIL import Image, ImageChops

# creating a image1 object
im1 = Image.open(r"C:\Users\sadow984\Desktop\a2.PNG")

# creating a image2 object
im2 = Image.open(r"C:\Users\sadow984\Desktop\x5.PNG")

# applying add method
im3 = ImageChops.add(im1, im2, scale = 4.0, offset = 4)

im3.show()
```

**输出:**
![](img/804b0c50b559a96f3c5f9aed039cc6de.png)

更多的比例和偏移值可以用于不同的目的。