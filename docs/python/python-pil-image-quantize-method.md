# Python PIL | Image.quantize()方法

> 原文:[https://www . geesforgeks . org/python-pil-image-quantify-method/](https://www.geeksforgeeks.org/python-pil-image-quantize-method/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**Image.quantize()**`用指定数量的颜色将图像转换为“P”模式。

> **语法:**图像.量化(颜色=256，方法=无，kmeans=0，调色板=无)
> 
> **参数**:
> 
> **颜色**–所需的颜色数量，< = 256
> **方法**–0 =中值切割 1 =最大覆盖 2 =快速八叉树
> **kman**–整数
> **调色板**–量化到 PIL。ImagingPalette 调色板。
> 
> **返回类型**:图像对象。

**所用图像:**
![](img/7dcee0f4c2b8e9d23dccc651065d73ab.png)

```py

# Importing Image module from PIL package 
from PIL import Image 
import PIL 

# creating a image object (main image) 
im1 = Image.open(r"C:\Users\System-Pc\Desktop\flower1.jpg") 

# quantize a image 
im1 = im1.quantize(256) 

# to show specified image 
im1.show() 
```

**输出:**
![](img/f2391f085c1db3c2eee5173dc410dcbe.png)