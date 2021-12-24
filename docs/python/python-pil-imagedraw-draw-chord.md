# Python PIL | ImageDraw。Draw.chord()

> 原文:[https://www . geesforgeks . org/python-pil-imagedraw-draw-chord/](https://www.geeksforgeeks.org/python-pil-imagedraw-draw-chord/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`ImageDraw`模块为图像对象提供简单的 2D 图形。您可以使用此模块创建新图像，注释或修饰现有图像，并动态生成图形以供网络使用。

`**ImageDraw.Draw.chord()**`与`arc()`相同，但用直线连接端点。

> **语法:** PIL。图像绘制。绘制。和弦(xy，开始，结束，填充=无，轮廓=无)
> 
> **参数:**
> **xy**–定义包围盒的四个点。[(x0，y0)，(x1，y1)]或[x0，y0，x1，y1]的序列。
> **轮廓**–用于轮廓的颜色。
> **填充**–用于填充的颜色。
> 
> **返回:**一个图像。

```py

# importing image object from PIL
import math
from PIL import Image, ImageDraw

w, h = 220, 190
shape = [(40, 40), (w - 10, h - 10)]

# creating new Image object
img = Image.new("RGB", (w, h))

# create chord image
img1 = ImageDraw.Draw(img)  
img1.chord(shape, start = 30, end = 200, fill ="# 800080", outline ="red")
img.show()
```

**输出:**
![](img/4cbbefb96173c5d8b26926ef18c69bb7.png)

**另一个例子:**这里我们使用不同的颜色进行填充。

```py

# importing image object from PIL
import math
from PIL import Image, ImageDraw

w, h = 220, 190
shape = [(40, 40), (w - 10, h - 10)]

# creating new Image object
img = Image.new("RGB", (w, h))

# create chord image
img1 = ImageDraw.Draw(img)  
img1.chord(shape, start = 30, end = 200, fill ="# ffff33", outline ="blue")
img.show()
```

**输出:**
![](img/dc24f9eb9f72d848d9687688dfe4c2a4.png)