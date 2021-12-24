# 魔杖自适应 _ 阈值()功能–Python

> 原文:[https://www . geesforgeks . org/wand-adaptive _ threshold-function-python/](https://www.geeksforgeeks.org/wand-adaptive_threshold-function-python/)

**adaptive_threshold()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于为每个像素应用阈值。它出现在课堂上*魔杖图像*。

> **语法:**
> 
> ```py
> adaptive_threshold(width, height, offset)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **宽度:**此参数用于指定宽度值，即 X 轴上相邻像素的大小。
> *   **高度:**此参数用于指定高度值，即 Y 轴上相邻像素的大小。
> *   **偏移量:**此参数用于指定偏移量的值，偏移量是介于 0.0 和 quantum_range 之间的归一化数。
>     如果值低于偏移量，它会强制像素变为黑色。
> 
> 注: *quantum_range* :是 ImageMagick 库支持的颜色通道的最大值。
> **返回值:**该函数返回魔杖图像魔法对象。

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
    with image.clone() as adaptive_threshold:
        # Invoke adaptive_threshold function with width as 2, height as
        # 3 and offset as 2
        adaptive_threshold.adaptive_threshold(2, 3, 2)
        # Save the image
        adaptive_threshold.save(filename ='adaptive_threshold1.jpg')
```

**输出:**

![](img/decf64d71ddc5f47b29d56550bba23a6.png)

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
        # Invoke adaptive_threshold function with width as 0, Height as 1 and offset as 0.3
        pic.adaptive_threshold(4, 5, 0.7)
        # Save the image
        pic.save(filename ='adaptive_threshold2.jpg')
```

**输出:**

![](img/743fb2e1560fa3353b5ba8e658b20261.png)