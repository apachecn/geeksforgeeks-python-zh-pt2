# 魔杖斩()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-chop-function-python/](https://www.geeksforgeeks.org/wand-chop-function-python/)

**chop()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于移除图像的一个区域。

> **语法:**
> 
> ```
> chop(width, height, x, y)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **宽度:**此参数存储区域的大小。
> *   **高度:**此参数存储区域的大小。
> *   **x:** 此参数存储图像的 x 偏移。
> *   **y:** 此参数存储图像的 y 偏移。
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
    with image.clone() as chop:
        # Invoke chop function
        chop.chop(300, 200, 15, 15)
        # Save the image
        chop.save(filename ='chop1.jpg')
```

**输出:**

![](img/3b0499a1d3e834a4f557549473351daf.png)

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
        # Invoke chop function
        pic.chop(300, 200, 20, 20)
        # Save the image
        pic.save(filename ='chop2.jpg')
```

**输出:**

![](img/241cddd2ba45bde300043e5d1c61d8b4.png)