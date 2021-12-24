# Python PIL |ImageDraw.Draw.multiline_textsize（）

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagedraw-draw-multiline _ text size/

**PIL 是 python 图像库**，为 Python 解释器提供图像编辑功能。`ImageDraw`模块为图像对象提供简单的 2D 图形。您可以使用此模块创建新图像，注释或修饰现有图像，并动态生成图形以供网络使用。

`**ImageDraw.Draw.multiline_textsize()**`返回给定字符串的大小，以像素为单位。

> **语法:**
> ImageDraw。Draw.multiline_textsize(文本，字体=无，间距=0)
> 
> **参数:**
> **文字**–待测文字。
> **字体**–一个 ImageFont 实例。
> **间距**–行与行之间的像素数。
> 
> **返回类型:**
> 返回带文字的图像。

**所用图像:**
![](img/29be814c699502ced0951c8a8e7955f9.png)

**代码:使用 ImageDraw。Draw.multiline_textsize**

```

# Importing Image and ImageFont, ImageDraw module from PIL package 
from PIL import Image, ImageFont, ImageDraw 

# creating a image object 
image = Image.open(r'C:\Users\System-Pc\Desktop\rose.jpg') 

draw = ImageDraw.Draw(image) 

#specified font size
font = ImageFont.truetype(r'C:\Users\System-Pc\Desktop\arial.ttf',30)

text =u"""\
ALWAYS BE HAPPY
(LAUGHING IS THE \n BEST MEDICINE)"""

# drawing text size
draw.text((20,18), text,font = None,spacing=0) 

image.show() 
```

**输出:**
![](img/78b9f7fb4acd0bf4b26c5ac83ffd1b0c.png)