# Python PIL | ImageDraw。Draw.pieslice()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagedraw-draw-pieslice/

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`ImageDraw`模块为图像对象提供简单的 2D 图形。您可以使用此模块创建新图像，注释或修饰现有图像，并动态生成图形以供网络使用。

`**ImageDraw.Draw.pieslice()**`与圆弧相同，但也在端点和边界框中心之间画直线。

> **语法:** PIL。图像绘制。绘制。切片(xy，开始，结束，填充=无，轮廓=无)
> 
> **参数:**
> **xy**–定义包围盒的四个点。[(x0，y0)，(x1，y1)]或[x0，y0，x1，y1]的序列。
> **开始**–开始角度，单位为度。角度从 3 点开始测量，顺时针方向增加。
> **终点**–终点角度，单位为度。
> **填充**–用于填充的颜色。
> **轮廓**–用于轮廓的颜色。
> 
> **返回:**切片形状的图像对象。

```

# importing image object from PIL
import math
from PIL import Image, ImageDraw

w, h = 220, 190
shape = [(40, 40), (w - 10, h - 10)]

# creating new Image object
img = Image.new("RGB", (w, h))

# create pieslice image
img1 = ImageDraw.Draw(img)  
img1.pieslice(shape, start = 50, end = 250, fill ="# ffff33", outline ="red")
img.show()
```

**输出:**
![](img/8a9a157729bb94ad7759d6c7c13800a6.png)

**另一个例子:**这里我们使用不同的颜色进行填充。

```

# importing image object from PIL
import math
from PIL import Image, ImageDraw

w, h = 220, 190
shape = [(40, 40), (w - 10, h - 10)]

# creating new Image object
img = Image.new("RGB", (w, h))

# create pieslice image
img1 = ImageDraw.Draw(img)  
img1.pieslice(shape, start = 50, end = 250, fill ="# 800080", outline ="white")
img.show()
```

**输出:**
![](img/0aa77a50163ad632fad715f6bacaa242.png)