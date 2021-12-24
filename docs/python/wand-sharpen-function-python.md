# 魔杖锐化()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-sharpen-function-python/](https://www.geeksforgeeks.org/wand-sharpen-function-python/)

**锐化()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于锐化图像。

> **语法:**
> 
> ```
> sharpen(radius, sigma)
> ```
> 
> **参数:**该函数接受上面提到的四个参数，定义如下:
> 
> *   **半径:**该参数存储锐度的半径值。
> *   **sigma:** 该参数存储锐化图像的 sigma 级别。
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
    with image.clone() as sharpen:
        # Invoke sharpen function with radius 50 and sigma 40
        sharpen.sharpen(50, 40)
        # Save the image
        sharpen.save(filename ='sharpen1.jpg')
```

**输出:**

![](img/852b124a5ba0c7a6a975be6db82d2587.png)

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
        # Invoke sharpen function method with radius 40 and sigma 30
        pic.sharpen(40, 30)
        # Save the image
        pic.save(filename ='sharpen2.jpg')
```

**输出:**

![](img/135f773776c40c2d4767223ff22ac3a4.png)