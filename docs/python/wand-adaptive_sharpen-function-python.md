# 魔杖自适应 _ 锐化()功能–Python

> 原文:[https://www . geeksforgeeks . org/wand-adaptive _ 锐化-function-python/](https://www.geeksforgeeks.org/wand-adaptive_sharpen-function-python/)

**adaptive _ 锐化()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于锐化图像。强度离边缘不远。它出现在课堂上*魔杖图像*。

> **语法:**
> 
> ```py
> adaptive_sharpen(radius, sigma, channel)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **半径:**此参数用于指定半径值，即高斯孔径的大小。
> *   **σ:**此参数用于指定σ的值，即高斯滤波器的标准偏差。
> *   **通道:**此参数用于将图像通道的值指定为未定义、‘红色’、‘灰色’、‘青色’、‘绿色’、‘品红色’、‘蓝色’、‘黄色’、‘alpha’、‘不透明度’、‘黑色’、‘索引’、‘composite _ channels’、‘all _ channels’、‘sync _ channels’、‘default _ channels’。
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
    with image.clone() as adaptive_sharpen:
        # Invoke adaptive_sharpen function with radius as 2, sigma as
        # 3 and channel as Green
        adaptive_sharpen.adaptive_sharpen(0, 3, 'Green')
        # Save the image
        adaptive_sharpen.save(filename ='adaptive_sharpen1.jpg')
```

**输出:**

![](img/da28763678d5d7eece90896aec119f0b.png)

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
        # Invoke adaptive_sharpen function with radius as 8, Sigma as 2
        # Channel as Red
        pic.adaptive_sharpen(8, 2, 'Red')
        # Save the image
        pic.save(filename ='adaptive_sharpen2.jpg')
```

**输出:**

![](img/c11b7d0c060760a78db70cfa345ee463.png)