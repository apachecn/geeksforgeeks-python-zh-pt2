# 魔杖去歪斜()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-deskew-function-python/](https://www.geeksforgeeks.org/wand-deskew-function-python/)

**去歪斜()**功能是 Python Wand ImageMagick 库中的内置功能，用于消除大多数扫描&光学导入设备常见的歪斜伪像。

> **语法:**
> 
> ```py
> edge(threshold)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **阈值:**该参数存储前景&背景之间的界限。范围从 0 到 1.0。
> 
> **返回值:**该函数返回魔杖图像图像对象。

**原图:**

![](img/2d3a0fdbc25c0bbb46c47454d1b0acc7.png)

**例 1:**

## 蟒蛇 3

```py
# Import library from Image
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:
    # Clone the image in order to process
    with image.clone() as deskew:
        # Invoke deskew function
        deskew.deskew(0.1)
        # Save the image
        deskew.save(filename ='deskew1.jpg')
```

**输出:**

![](img/334a89259158b599673b7876ce9a22dd.png)

**例 2:**

## 蟒蛇 3

```py
# Import libraries from the wand 
from wand.image import Image
from wand.drawing import Drawing
from wand.color import Color

with Drawing() as draw:
    # Set Stroke color the circle to black
    draw.stroke_color = Color('black')
    # Set Width of the circle to 2
    draw.stroke_width = 1
    # Set the fill color to 'White (# FFFFFF)'
    draw.fill_color = Color('white')

    # Invoke Circle function with center at 50, 50 and radius 25
    draw.circle((200, 200), # Center point
                (100, 100)) # Perimeter point
    # Set the font style
    draw.font = '../Helvetica.ttf'
    # Set the font size
    draw.font_size = 30

    with Image(width = 400, height = 400, background = Color('# 45ff33')) as pic:
        # Set the text and its location
        draw.text(int(pic.width / 3), int(pic.height / 2), 'GeeksForGeeks !')
        # Draw the picture
        draw(pic)
        # Invoke deskew function
        pic.deskew(0.7)
        # Save the image
        pic.save(filename ='deskew2.jpg')
```

**输出:**

![](img/f62308bf8d3069274b59dd1516cf8010.png)