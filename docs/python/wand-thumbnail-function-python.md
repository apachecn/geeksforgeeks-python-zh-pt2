# 魔杖缩略图()功能–Python

> 原文:[https://www . geesforgeks . org/wand-thumbnail-function-python/](https://www.geeksforgeeks.org/wand-thumbnail-function-python/)

**缩略图()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于制作给定图像的缩略图。

> **语法:**
> 
> ```py
> thumbnail(width, height)
> ```
> 
> **参数:**该函数接受上面提到的四个参数，定义如下:
> 
> *   **宽度:**此参数存储缩略图的宽度。
> *   **高度:**此参数存储缩略图的高度。
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
    with image.clone() as thumbnail:
        # Invoke thumbnail function with x as 50 and y as 50
        thumbnail.thumbnail(50, 50)
        # Save the image
        thumbnail.save(filename ='thumbnail1.jpg')
```

**输出:**

![](img/6ac4f9950aab43e58d1714d6ab2e7fce.png)

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
        # Invoke thumbnail function with x as 50 and y as 50
        pic.thumbnail(50, 50)
        # Save the image
        pic.save(filename ='thumbnail2.jpg')
```

**输出:**

![](img/54efbfd07534040a8c55f48283947db1.png)