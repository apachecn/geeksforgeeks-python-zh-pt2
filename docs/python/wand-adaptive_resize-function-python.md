# 魔杖自适应 _ 调整大小()功能–Python

> 原文:[https://www . geeksforgeeks . org/wand-adaptive _ resize-function-python/](https://www.geeksforgeeks.org/wand-adaptive_resize-function-python/)

**adaptive_resize()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过网格插值技术调整图像的大小。它出现在课堂上*魔杖图像*。

> **语法:**
> 
> ```
> adaptive_resize(columns, rows)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **列:**此参数用于指定调整大小后图像的宽度值。
> *   **行:**此参数用于指定调整大小后图像的高度值。
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
    with image.clone() as adaptive_resize:
        # Invoke adaptive_resize function with columns as 1024, rows as 768
        adaptive_resize.adaptive_resize(1024, 768)
        # Save the image
        adaptive_resize.save(filename ='adaptive_resize1.jpg')
```

**输出:**

![](img/9051cc1243bab3e586c7287cc02b7dbb.png)

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
        # Invoke Adaptive Resize function with columns as 800, rows as 800
        pic.adaptive_resize(800, 800)
        # Save the image
        pic.save(filename ='adaptive_resize2.jpg')
```

**输出:**

![](img/3d35cae6f5a33dc70a9cde797e9a3b7a.png)