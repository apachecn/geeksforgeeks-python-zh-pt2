# python pil | imagecolor . info GB()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagecolor-info GB 方法/

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`ImageColor`模块包含颜色表和从 CSS3 风格的颜色说明符到 RGB 元组的转换器。该模块由`PIL.Image.Image.new()`和`ImageDraw`模块使用。

`**ImageColor.getrgb()**`将颜色字符串转换为 RGB 元组。如果字符串无法解析，该函数将引发`ValueError`异常。

> 语法:GDP。image color . image GB(颜色)
> 
> **参数:**
> **颜色**–一个颜色串
> 
> **返回:**(红、绿、蓝[，α])

```py

# importing Image module from PIL package 
from PIL import Image, ImageColor

# using getrgb
im = ImageColor.getrgb("orange")
print(im)

im1 = ImageColor.getrgb("red")
print(im1)
```

**输出:**

```py
(255, 165, 0)
(255, 0, 0)

```

**另一个例子:**–这里用了不同的颜色。

```py

# importing Image module from PIL package 
from PIL import Image, ImageColor

# using getrgb
im = ImageColor.getrgb("blue")
print(im)

im1 = ImageColor.getrgb("yellow")
print(im1)
```

**输出:**

```py
(0, 0, 255)
(255, 255, 0)

```