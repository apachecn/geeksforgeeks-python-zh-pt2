# 魔杖阈值()函数–Python

> 原文:[https://www . geesforgeks . org/wand-threshold-function-python/](https://www.geeksforgeeks.org/wand-threshold-function-python/)

**threshold()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于修改图像，使得任何大于阈值的像素强度值都被指定为最大强度(白色)，或者被指定为最小强度(黑色)。

> **语法:**
> 
> ```
> threshold(threshold, channel)
> ```
> 
> **参数:**该函数接受上面提到的四个参数，定义如下:
> 
> *   **阈值:**该参数存储 0 到 1.0 之间的阈值量。
> *   **高度:**此参数存储缩略图的高度。
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
    with image.clone() as threshold:
        # Invoke threshold function with threshold as 0.3 and channel as 'green'
        threshold.threshold(0.3, 'green')
        # Save the image
        threshold.save(filename ='threshold1.jpg')
```

**输出:**

![](img/1b8136b5236b83da43dfd91b252f2fd3.png)

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
        # Invoke threshold function with threshold as 0.5 and channel as 'green'
        pic.threshold(0.5, 'green')
        # Save the image
        pic.save(filename ='threshold2.jpg')
```

**输出:**

![](img/bc40d0fc30dd6b3526c2280e7a72ccf6.png)