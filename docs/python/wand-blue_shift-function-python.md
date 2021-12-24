# 魔杖蓝移()功能–Python

> 原文:[https://www . geesforgeks . org/wand-blue _ shift-function-python/](https://www.geeksforgeeks.org/wand-blue_shift-function-python/)

**blue_shift()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于淡化图像的颜色。

> **语法:**
> 
> ```py
> blue_shift(factor)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **因子:**该参数用于指定因子的值，以便应用暗淡度。
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
    with image.clone() as blue_shift:
        # Invoke blue_shift function with radius as 10, sigma as 12
        # channel as 'Green'
        blue_shift.blue_shift(factor = 1.8)
        # Save the image
        blue_shift.save(filename ='blue_shift1.jpg')
```

**输出:**

![](img/5b60b0750291549be1fd2ac9217601e7.png)

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
        # Invoke blue_shift function with factor 2
        pic.blue_shift(factor = 2)
        # Save the image
        pic.save(filename ='blue_shift2.jpg')
```

**输出:**

![](img/eba9b704706b40551dc75a8463450aa8.png)