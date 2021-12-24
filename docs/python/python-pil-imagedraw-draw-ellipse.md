# Python PIL | ImageDraw。Draw.ellipse()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagedraw-draw-ellipse/

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`ImageDraw`模块为图像对象提供简单的 2D 图形。您可以使用此模块创建新图像，注释或修饰现有图像，并动态生成图形以供网络使用。

`**ImageDraw.Draw.ellipse()**`在给定的边界框内绘制一个椭圆。

> **语法:** PIL。图像绘制。绘制。椭圆(xy，填充=无，轮廓=无)
> 
> **参数:**
> **xy**–定义包围盒的四个点。[(x0，y0)，(x1，y1)]或[x0，y0，x1，y1]的序列。
> **轮廓**–用于轮廓的颜色。
> **填充**–用于填充的颜色。
> 
> **返回:**椭圆形状的图像对象。

```py

# importing image object from PIL
import math
from PIL import Image, ImageDraw

w, h = 220, 190
shape = [(40, 40), (w - 10, h - 10)]

# creating new Image object
img = Image.new("RGB", (w, h))

# create ellipse image
img1 = ImageDraw.Draw(img)  
img1.ellipse(shape, fill ="# ffff33", outline ="red")
img.show()
```

**输出:**
![](img/52669a9fca6225e1b82f2dc5023b3a30.png)

**另一个例子:**这里我们使用不同的颜色进行填充。

```py

# importing image object from PIL
import math
from PIL import Image, ImageDraw

w, h = 220, 190
shape = [(40, 40), (w - 10, h - 10)]

# creating new Image object
img = Image.new("RGB", (w, h))

# create ellipse image
img1 = ImageDraw.Draw(img)  
img1.ellipse(shape, fill ="# 800080", outline ="green")
img.show()
```

**输出:**
![](img/a7f6bba074206753c3793d7669f34892.png)