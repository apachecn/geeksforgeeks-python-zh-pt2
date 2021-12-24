# 魔杖展开()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-spread-function-python/](https://www.geeksforgeeks.org/wand-spread-function-python/)

**spread()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于用相邻像素值的统计结果替换每个像素。宽度&高度定义了相邻像素的大小或孔径。

> **语法:**
> 
> ```py
> spread(radius, method)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **半径:**该参数存储像素可以从源位置位移的半径。
> *   **方法:**此参数存储可用的颜色方法。一些可用的方法是“未定义”、“平均”、“平均 9”、“平均 16”、“背景”、“双线性”、“混合”、“catrom”、“整数”、“网格”、“最近”、“样条线”。
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
    with image.clone() as spread:
        # Invoke spread function with radius 15 and method as 'nearest'
        spread.spread(15, 'nearest')
        # Save the image
        spread.save(filename ='spread1.jpg')
```

**输出:**

![](img/769f198d24f88b637da7fdf0e3c71c19.png)

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
        # Invoke spread function with radius 10 and method as 'blend'
        pic.spread(10, 'blend')
        # Save the image
        pic.save(filename ='spread2.jpg')
```

**输出:**

![](img/71b4d4f4fbc34ed824ae01ce918f9c53.png)