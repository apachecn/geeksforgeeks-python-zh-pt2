# python pil | imagechops . constant()

> 原文:[https://www . geesforgeks . org/python-pil-image chops-constant/](https://www.geeksforgeeks.org/python-pil-imagechops-constant/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**PIL.ImageChops.constant()**`用给定的灰度级填充通道。

> **语法:** PIL。ImageChops.constant(图像，值)
> 
> **参数:**
> **图像**–取一个有扩展类型的图像。
> 
> **返回:**一个图像。

**所用图像:**
![](img/0987b2cabac0e902aa04bda46e015f55.png)

```

# importing image object from PIL
from PIL import Image, ImageChops  

# creating an image object 
img = Image.open(r"C:\Users\System-Pc\Desktop\TREE.JPG") 
img1 = ImageChops.constant(img, 60) 

img1.show() 
```

**输出:**
![](img/628fae6a472aad01bc0e5961862294e9.png)

**另一个例子:**取另一幅不同值的图像，看灰度的变化。

**所用图像:**
![](img/2a9df8c1256221871affe64d76866928.png)

```

# importing image object from PIL
from PIL import Image, ImageChops  

# creating an image object 
img = Image.open(r"C:\Users\System-Pc\Desktop\rose.jpg") 
img1 = ImageChops.constant(img, 200) 

img1.show() 
```

**输出:**
![](img/2bab07125a0065067952fbe7b14d5ff4.png)