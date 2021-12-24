# Python PIL | ImageDraw。Draw.text()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-imagedraw-draw-text/

PIL 是 python 图像库，为 Python 解释器提供图像编辑功能。`ImageDraw`模块为图像对象提供简单的 2D 图形。您可以使用此模块创建新图像，注释或修饰现有图像，并动态生成图形以供网络使用。

`**ImageDraw.Draw.text()**`在给定位置绘制字符串。

> **语法:**
> ImageDraw。绘图.文本(xy，文本，填充=无，字体=无，定位=无，间距=0，对齐=“左”)
> 
> **参数:**
> **xy**–文本左上角。
> **文本**–要绘制的文本。如果包含任何换行符，文本将被传递到 multiline_text()
> **填充**–用于文本的颜色。
> **字体**–一个 ImageFont 实例。
> **间距**–如果文本传递给 multiline_text()，则为行与行之间的像素数。
> **对齐**–如果文本传递到 multiline_text()，“左”、“中”或“右”。
> 
> **返回类型:**
> 返回带文字的图像。

**所用图像:**
![](img/29be814c699502ced0951c8a8e7955f9.png)

**代码:使用 PIL | ImageDraw。Draw.text()**

```

# Importing Image and ImageFont, ImageDraw module from PIL package 
from PIL import Image, ImageFont, ImageDraw 

# creating a image object 
image = Image.open(r'C:\Users\System-Pc\Desktop\rose.jpg') 

draw = ImageDraw.Draw(image) 

# specified font size
font = ImageFont.truetype(r'C:\Users\System-Pc\Desktop\arial.ttf', 20) 

text = 'LAUGHING IS THE \n BEST MEDICINE'

# drawing text size
draw.text((5, 5), text, font = font, align ="left") 

image.show() 
```

**输出:**
![](img/fb49ceb8cc27871ff5abdb41dde89c54.png)

**另一个例子:**这里我们改变参数。

**所用图像:**
![](img/64b3f3bce0ca2a6b2d4cabacd43196ff.png)

**代码:使用 PIL | ImageDraw。Draw.text()**

```

# Importing Image and ImageFont, ImageDraw module from PIL package 
from PIL import Image, ImageFont, ImageDraw 

# creating a image object 
image = Image.open(r'C:\Users\System-Pc\Desktop\flower.jpg') 

draw = ImageDraw.Draw(image) 

# specified font size
font = ImageFont.truetype(r'C:\Users\System-Pc\Desktop\arial.ttf', 20) 

text = 'LAUGHING IS THE \n BEST MEDICINE'

# drawing text size
draw.text((5, 5), text, fill ="red", font = font, align ="right") 

image.show() 
```

**输出:**
![](img/c9cfa579b2b23304c8f5ac7959359d15.png)