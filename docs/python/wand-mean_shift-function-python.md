# Wand mean_shift()函数–Python

> 原文:[https://www . geesforgeks . org/wand-mean _ shift-function-python/](https://www.geeksforgeeks.org/wand-mean_shift-function-python/)

**mean_shift()** 函数是 Python Wand ImageMagick 库中的内置函数，用于通过比较颜色距离内的相邻像素并用平均值替换来重新计算像素值。

> **语法:**
> 
> ```py
> mean_shift(width, height, color_distance)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **宽度:**此参数用于以像素为单位存储邻域窗口的宽度。
> *   **高度:**此参数用于以像素为单位存储邻域窗口的高度。
> *   **color_distance:** 该参数用于存储该颜色距离内的像素值。
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
    with image.clone() as mean_shift:
        # Invoke mean_shift function with width as 30 and height as 10
        # and color_distance as 0.2
        mean_shift.mean_shift(30, 10, 0.2)
        # Save the image
        mean_shift.save(filename ='mean_shift1.jpg')
```

**输出:**

![](img/a02ff10d7b8caec89d267b698ea92c8d.png)

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
        # Invoke mean_shift function with width as 20, height as 30 and color_distance as 0.6
        pic.mean_shift(20, 30, 0.6)
        # Save the image
        pic.save(filename ='mean_shift2.jpg')
```

**输出:**

![](img/887afaa6fff68b9829b79d5f496aeec0.png)