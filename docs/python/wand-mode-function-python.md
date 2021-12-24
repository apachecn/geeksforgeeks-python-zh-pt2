# 魔杖模式()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-mode-function-python/](https://www.geeksforgeeks.org/wand-mode-function-python/)

**模式()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于用相邻颜色的数学模式替换每个像素。

> **语法:**
> 
> ```py
> mode(width, height)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **宽度:**此参数用于存储模式中要包含的相邻像素数量。
> *   **高度:**这是一个可选参数，用于存储相邻像素的高度。默认情况下，它与宽度相同。
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
    with image.clone() as mode:
        # Invoke mode function with width as 30 and height as 10
        mode.mode(30, 10)
        # Save the image
        mode.save(filename ='mode1.jpg')
```

**输出:**

![](img/9f85aca9c5a0958ef3101d8b84b5c1e5.png)

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
        # Invoke mode function with width and height as 200
        pic.mode(200)
        # Save the image
        pic.save(filename ='mode2.jpg')
```

**输出:**

![](img/3ee450d36caf56eaaaa2769a90731533.png)