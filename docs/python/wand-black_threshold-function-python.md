# 魔杖黑 _ 阈值()功能–Python

> 原文:[https://www . geesforgeks . org/wand-black _ threshold-function-python/](https://www.geeksforgeeks.org/wand-black_threshold-function-python/)

**black_threshold()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于强制给定颜色以上的所有像素为黑色，并保持阈值以上的所有像素不变。

> **语法:**
> 
> ```py
> black_threshold(color)
> ```
> 
> **参数:**该功能接受上述单个参数，定义如下:
> 
> *   **颜色:**该参数用于指定因子的值，以便应用黑色阈值。此参数接受诸如“绿色”、“蓝色”、“红色”、“白色”等颜色字符串的值。
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
    with image.clone() as black_threshold:
        # Invoke black_threshold function with threshold parameter as 'Green'
        black_threshold.black_threshold('Green')
        # Save the image
        black_threshold.save(filename ='black_threshold1.jpg')
```

**输出:**

![](img/35c23f3ce70efb7a7717a30634fe94c5.png)

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
        # Invoke black_threshold function with with threshold parameter as 'White'
        pic.black_threshold('White')
        # Save the image
        pic.save(filename ='black_threshold2.jpg')
```

**输出:**

![](img/23a0155ba385da6cbfdfb0f81bc2f946.png)