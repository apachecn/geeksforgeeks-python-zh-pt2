# Wand local_contrast()函数–Python

> 原文:[https://www . geesforgeks . org/wand-local _ contrast-function-python/](https://www.geeksforgeeks.org/wand-local_contrast-function-python/)

**local_contrast()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于增加图像中的明暗过渡。

> **语法:**
> 
> ```
> local_contrast(radius, strength)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **半径:**此参数用于存储高斯算子的大小。默认值为 10.0
> *   **强度:**此参数用于存储要应用的模糊蒙版的百分比。默认值为 12.5，范围从 0 到 100。
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
    with image.clone() as local_contrast:
        # Invoke local_contrast function with radius 12 and sigma 3
        local_contrast.local_contrast(12, 3)
        # Save the image
        local_contrast.save(filename ='local_contrast1.jpg')
```

**输出:**

![](img/f42f7e3d7d5848cad4f8581a448d54e6.png)

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
        # Invoke local_contrast function with radius 15 and sigma 78
        pic.local_contrast(15, 78)
        # Save the image
        pic.save(filename ='local_contrast2.jpg')
```

**输出:**

![](img/a02e1d077a9c72043685fb94690353b5.png)