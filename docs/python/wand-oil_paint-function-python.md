# 魔杖油彩()功能–Python

> 原文:[https://www . geesforgeks . org/wand-oil _ paint-function-python/](https://www.geeksforgeeks.org/wand-oil_paint-function-python/)

**oil_paint()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过用最频繁的周围颜色替换每个像素来模拟一幅油画。

> **语法:**
> 
> ```py
> oil_paint(radius, sigma)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **半径:**该参数用于存储仿真的半径。
> *   **σ:**该参数用于存储仿真的σ。
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
    with image.clone() as oil_paint:
        # Invoke oil_paint function with radius 6 and sigma 4
        oil_paint.oil_paint(6, 4)
        # Save the image
        oil_paint.save(filename ='oil_paint1.jpg')
```

**输出:**

![](img/7025917ff222d292ac386ab7fa4a1577.png)

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
        # Invoke oil_paint function with radius 9 and sigma 7
        pic.oil_paint(9, 7)
        # Save the image
        pic.save(filename ='oil_paint2.jpg')
```

**输出:**

![](img/37d8882ece8e705f3f34bef9af5b4bff.png)