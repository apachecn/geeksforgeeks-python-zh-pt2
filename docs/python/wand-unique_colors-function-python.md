# 魔杖独有 _colors()功能–Python

> 原文:[https://www . geesforgeks . org/wand-unique _ colors-function-python/](https://www.geeksforgeeks.org/wand-unique_colors-function-python/)

**unique_colors()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于丢弃所有重复的像素。它将图像重建为单行。

> **语法:**
> 
> ```
> unique_colors()
> ```
> 
> **参数:**此功能不接受任何参数。
> **返回值:**该函数返回魔杖图像魔法对象。

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
    with image.clone() as unique_colors:
        # Invoke unique_colors function
        unique_colors.unique_colors()
        # Save the image
        unique_colors.save(filename ='unique_colors1.jpg')
```

**输出:**

![](img/d0f522a129d4f47888f88f57fb46bc63.png)

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
        # Invoke unique_colors() function
        pic.unique_colors()
        # Save the image
        pic.save(filename ='unique_colors2.jpg')
```

**输出:**

![](img/ac25ca3d2c0e6237f51e452648c63a2c.png)