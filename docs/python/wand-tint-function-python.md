# 魔杖着色()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-tint-function-python/](https://www.geeksforgeeks.org/wand-tint-function-python/)

**tint()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于对图像中的每个像素应用颜色矢量。

> **语法:**
> 
> ```
> tint(color, alpha)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **颜色:**该参数存储计算中间色调的颜色。
> *   **alpha:** 此参数存储决定如何混合的颜色。
> 
> **返回值:**该函数返回魔杖图像图像对象。

**原图:**

![](img/2d3a0fdbc25c0bbb46c47454d1b0acc7.png)

**例 1:**

## 蟒蛇 3

```
# Import library from Image
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:
    # Clone the image in order to process
    with image.clone() as tint:
        # Invoke tint function with radius as 'green' and alpha as 'white'
        tint.tint('green', 'white')
        # Save the image
        tint.save(filename ='tint1.jpg')
```

**输出:**

![](img/eb834772b23a16235c9881a488b1a912.png)

**例 2:**

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
        # Invoke tint function with radius as 'green', alpha as 'white'
        pic.tint('green', 'white')
        # Save the image
        pic.save(filename ='tint2.jpg')
```

**输出:**

![](img/f06634b791475499b1256f326f4be7dd.png)