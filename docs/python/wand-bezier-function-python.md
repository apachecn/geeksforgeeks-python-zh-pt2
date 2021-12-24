# 魔杖贝塞尔()函数–Python

> 原文:[https://www.geeksforgeeks.org/wand-bezier-function-python/](https://www.geeksforgeeks.org/wand-bezier-function-python/)

**贝塞尔()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于从指定点绘制贝塞尔曲线。

> **语法:**
> 
> ```
> bezier(points)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **点:**此参数用于指定点的值。它属于列表类型，用于声明点的数组。
> 
> **返回值:**该函数返回魔杖图像图像对象。

**例 1:**

## 蟒蛇 3

```
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
    # Set the bezier points as (x, y)
    points = [(40, 200), # Start point
    (120, 110), # First control
    (190, 180), # Second control
    (210, 360), # Third control
    (240, 240), # Fourth control
    (370, 140)] # End point

    # Set the font style
    draw.font = '../Helvetica.ttf'
    # Set the font size
    draw.font_size = 30

    with Image(width = 400, height = 400, background = Color('# 45ff33')) as pic:
        # Set the text and its location
        draw.text(int(pic.width / 3), int(pic.height / 8), 'GFG-BezierCurve')
        # Invoke bezier function with declared points
        draw.bezier(points)
        # Draw the picture
        draw(pic)
        # Save the image
        pic.save(filename ='bezier1.jpg')
```

**输出:**

![](img/276bbde25f09740c5da2b0839badfb55.png)