# Python PIL | blend()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-blend-method/](https://www.geeksforgeeks.org/python-pil-blend-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. **PIL.Image.blend()** method creates a new image by interpolating between two input images, using a constant alpha.

> **语法:** PIL。Image.blend(image1，image2，alpha)。
> 
> **参数:**
> **image1:** 第一张图像
> **image2:** 第二张图像，**必须与第一张图像具有相同的模式和大小。**
> **α:**内插α因子。如果 alpha 为 0.0，则返回第一个图像的副本。如果 alpha 为 1.0，则返回第二个图像的副本。阿尔法值没有限制。如有必要，结果将被裁剪以适合允许的输出范围。

图片 1:
![](img/ab052e5d861a012714522e1595c88749.png)

图片 2:
![](img/a8be9eb8b4d8e76ac182ce7af1b31a65.png)

```
# Importing Image module from PIL package 
from PIL import Image

# creating a image1 object and convert it to mode 'P'
im1 = Image.open(r"C:\Users\sadow984\Desktop\i2.PNG").convert('L')

# creating a image2 object and convert it to mode 'P'
im2 = Image.open(r"C:\Users\sadow984\Desktop\c2.PNG").convert('L')

# alpha is 0.0, a copy of the first image is returned
im3 = Image.blend(im1, im2, 0.0)

# to show specified image 
im3.show()
```

**输出:**
![](img/8f384972a269e8dd5abf8d6949271806.png)

```
# Importing Image module from PIL package 
from PIL import Image

# creating a image1 object and convert it to mode 'P'
im1 = Image.open(r"C:\Users\sadow984\Desktop\i2.PNG").convert('L')

# creating a image2 object and convert it to mode 'P' 
im2 = Image.open(r"C:\Users\sadow984\Desktop\c2.PNG").convert('L')

# alpha is 1.0, a copy of the second image is returned
im3 = Image.blend(im1, im2, 0.0)

# to show specified image 
im3.show()
```

**输出:**
![](img/3adffcef3bef392f1bd5eb0af60579dc.png)