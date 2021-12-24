# Python PIL |复合()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-composite-method/](https://www.geeksforgeeks.org/python-pil-composite-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. `**PIL.Image.composite()**` method creates composite image by blending images using a transparency mask. Here, mask is another image which remains transparent when composite together.

> **语法:** PIL。Image.composite(image1，image2，mask)
> 
> **参数:**
> **image1**–第一张图片。
> **图像 2**–第二个图像。**必须与第一张图像具有相同的模式和大小。**
> **遮罩**–一个遮罩图像。该图像可以有模式“1”、“L”或“RGBA”，并且**必须与其他两张图像具有相同的大小。**

```py
# Importing Image module from PIL package
from PIL import Image

# creating a image1 object and converting it to mode 'L'
im1 = Image.open(r"C:\Users\sadow984\Desktop\c2.PNG").convert('L')

im1.show()
```

显示图像 1:
![](img/429331fb727f95658720233266f4c843.png)

```py
# Importing Image module from PIL package
from PIL import Image

# creating a image1 object and converting it to mode 'L'
im2 = Image.open(r"C:\Users\sadow984\Desktop\i2.PNG").convert('L')
im2.show()
```

显示图像 2:
![](img/48745951a0cbcc513c3c225a3df047d7.png)

```py
# Importing Image module from PIL package
from PIL import Image

# creating a image1 object and converting it to mode 'L'
mask = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG").convert('L')
mask.show()
```

显示蒙版图像:
![](img/7ed8ffb8198df212ed45124c22f1dcb0.png)

```py
# Importing Image module from PIL package
from PIL import Image

# creating a image1 object and converting it to mode 'L'
im1 = Image.open(r"C:\Users\sadow984\Desktop\c2.PNG").convert('L')

# creating a image2 object and converting it to mode 'L'
im2 = Image.open(r"C:\Users\sadow984\Desktop\i2.PNG").convert('L')

# creating a mask image object and converting it to mode 'L'
mask = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG").convert('L')

# compositing all the three images
im3 = Image.composite(im1, im2, mask)

# to show specified image 
im3.show()
```

**输出:**【合成图像】
![](img/a77167ba4e1297bf469f93bd48aee947.png)