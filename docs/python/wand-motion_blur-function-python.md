# 魔杖运动模糊()功能–Python

> 原文:[https://www . geesforgeks . org/wand-motion _ blur-function-python/](https://www.geeksforgeeks.org/wand-motion_blur-function-python/)

**运动模糊()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于模拟运动模糊。该函数将图像与给定半径和标准偏差的高斯算子卷积。

> **语法:**
> 
> ```
> motion_blur(radius, sigma, angle)
> ```
> 
> **参数:**该函数接受三个参数，如上所述，定义如下:
> 
> *   **半径:**该参数用于存储高斯半径，单位为像素。
> *   **σ:**该参数用于求高斯的标准差，单位为像素。
> *   **角度:**此参数沿此角度应用效果。
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
    with image.clone() as motion_blur:
        # Invoke motion_blur function with radius 25, sigma 3 and angle 45
        motion_blur.motion_blur(25, 3, 45)
        # Save the image
        motion_blur.save(filename ='motion_blur1.jpg')
```

**输出:**

![](img/b5df7d71ac9f2ca66d7231dd8a4cab24.png)

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
        # Invoke motion_blur function with radius 30, sigma 4 and angle 260
        pic.motion_blur(30, 4, 260)
        # Save the image
        pic.save(filename ='motion_blur2.jpg')
```

**输出:**

![](img/b5744d4d5d3d1e24c36d016288626db2.png)