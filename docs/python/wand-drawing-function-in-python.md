# Python 中的魔杖绘图()功能

> 原文:[https://www . geesforgeks . org/wand-drawing-function-in-python/](https://www.geeksforgeeks.org/wand-drawing-function-in-python/)

魔杖的另一个模块是魔杖绘图。这个模块为我们提供了一些非常基本的绘图功能。绘制对象缓冲将形状绘制成图像的指令，然后它可以将这些形状绘制成零个或多个图像。

> **语法:**以 draw()为 draw:

> 注意:在上面的语法中，“as draw”只是一个命名法，根据需要可以是任何字符串。Python 棒取中的绘图函数没有参数。

**示例#1:**

```py
# Import important objects from wand library
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

# Create draw object using Drawing() function
with Drawing() as draw:
    with Image(width = 200,
               height = 200,
               background = Color('green')) as img:
        draw(img)
        img.save(filename ='empty.gif')
```

**输出图像:**
![](img/d3e11a791a22aa7c62dcf70b75493eae.png)

让我们划一条线

**例 2:**

```py
# Import important objects from wand library
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

# Create draw object using Drawing() function
with Drawing() as draw:
    draw.stroke_color = Color('black')
    draw.stroke_width = 2
    draw.line((5, 5), (45, 50))
    with Image(width = 200,
               height = 200,
               background = Color('green')) as img:
        draw.draw(img)
        img.save(filename ='line.gif')
```

**输出图像:**
![](img/dc9d344f646962fe0f2c54827087e1bf.png)