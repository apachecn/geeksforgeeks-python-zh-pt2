# 魔杖棕褐色 _tone()功能–Python

> 原文:[https://www . geesforgeks . org/wand-sepia _ tone-function-python/](https://www.geeksforgeeks.org/wand-sepia_tone-function-python/)

**棕褐色色调()**函数是 Python 棒 ImageMagick 库中的一个内置函数，用于创建棕褐色色调效果。

> **语法:**
> 
> ```
> sepia_tone(threshold)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **阈值:**该参数存储效果的阈值。
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
    with image.clone() as sepia_tone:
        # Invoke sepia_tone function with threshold as 0.8
        sepia_tone.sepia_tone(0.8)
        # Save the image
        sepia_tone.save(filename ='sepia_tone1.jpg')
```

**输出:**

![](img/c5e5b224a597ce93a4526e0f56a8f113.png)

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
        # Invoke sepia_tone function method with threshold 0.6
        pic.sepia_tone(0.6)
        # Save the image
        pic.save(filename ='sepia_tone2.jpg')
```

**输出:**

![](img/4f3c054a42a387a54e59c750e31defcc.png)