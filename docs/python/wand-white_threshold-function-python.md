# Wand white_threshold()函数–Python

> 原文:[https://www . geesforgeks . org/wand-white _ threshold-function-python/](https://www.geeksforgeeks.org/wand-white_threshold-function-python/)

**white_threshold()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于强制阈值以上的所有像素变为白色，同时保持阈值以下的所有像素不变。

> **语法:**
> 
> ```
> white_threshold(color)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **颜色:**此参数将颜色值存储为字符串，如“绿色”、“白色”、“红色”。
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
    with image.clone() as white_threshold:
        # Invoke white_threshold function with "Green" color
        white_threshold.white_threshold("green")
        # Save the image
        white_threshold.save(filename ='white_threshold1.jpg')
```

**输出:**

![](img/52ca0dc28ca87907e969b0ac5eea38af.png)

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
        # Invoke white_threshold function with "red" color
        pic.white_threshold("red")
        # Save the image
        pic.save(filename ='white_threshold2.jpg')
```

**输出:**

![](img/e68772baadb788fb169571fda485f82f.png)