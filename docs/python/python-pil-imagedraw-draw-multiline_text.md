# Python PIL |ImageDraw.Draw.multiline_text（）

> 原文:[https://www . geesforgeks . org/python-pil-imagedraw-draw-multiline _ text/](https://www.geeksforgeeks.org/python-pil-imagedraw-draw-multiline_text/)

PIL 是 python 图像库，为 Python 解释器提供图像编辑功能。`ImageDraw`模块为图像对象提供简单的 2D 图形。您可以使用此模块创建新图像，注释或修饰现有图像，并动态生成图形以供网络使用。

`**ImageDraw.Draw.multiline_text()**`在给定位置绘制字符串。

> **语法:**
> ImageDraw。Draw.multiline_text(xy，文本，填充=无，字体=无，定位=无，间距=0，对齐=“左”)
> 
> **参数:**
> 
> **xy**–文本左上角。
> **文字**–待画文字。
> **填充–用于文本的颜色。
> **字体**–一个 ImageFont 实例。
> **间距**–行与行之间的像素数。
> **对齐**–如果文本传递到 multiline_text()，“左”、“中”或“右”。**
> 
> ****返回类型:**–
> 返回带文本的图像。**

****所用图像:**
![](img/29be814c699502ced0951c8a8e7955f9.png)**

****代码:ImageDraw 示例。Draw.multiline_text()****

```

# Importing Image and ImageFont, ImageDraw module from PIL package 
from PIL import Image, ImageFont, ImageDraw 

# creating a image object 
image = Image.open(r'C:\Users\System-Pc\Desktop\ROSE.jpg') 

draw = ImageDraw.Draw(image) 

# specified font size
font = ImageFont.truetype(r'C:\Users\System-Pc\Desktop\arial.ttf', 15) 
spacing = 50
text = u"""\
ALWAYS BE HAPPY
(LAUGHING IS THE \n BEST MEDICINE)"""

# drawing text size
draw.text((6, 8), text, fill ="red", font = font, 
          spacing = spacing, align ="right") 

image.show() 
```

****输出:**
![](img/e31ddd86e817066aedcafddbfc4c5c9d.png)**

****另一个例子:**这里我们改变参数。**

****所用图像:**
![](img/64b3f3bce0ca2a6b2d4cabacd43196ff.png)**

****代码:ImageDraw 示例。Draw.multiline_text()****

```

# Importing Image and ImageFont, ImageDraw module from PIL package 
from PIL import Image, ImageFont, ImageDraw 

# creating a image object 
image = Image.open(r'C:\Users\System-Pc\Desktop\flower.jpg') 

draw = ImageDraw.Draw(image) 

# specified font size
font = ImageFont.truetype(r'C:\Users\System-Pc\Desktop\arial.ttf', 15) 
spacing = 50
text = u"""\
ALWAYS BE HAPPY
(LAUGHING IS THE \n BEST MEDICINE)"""

# drawing text size
draw.text((6, 8), text, fill ="black", 
          font = font, spacing = spacing, align ="right") 

image.show() 
```

****输出:**
![](img/adea4fc948999053fd0898cf52f9a145.png)**