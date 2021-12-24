# 魔杖日晒()功能–Python

> 原文:[https://www . geesforgeks . org/wand-solarize-function-python/](https://www.geeksforgeeks.org/wand-solarize-function-python/)

**solarize()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于否定阈值级别以上的所有像素。

> **语法:**
> 
> ```
> solarize(threshold, channel)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **阈值:**此参数存储从 0 到可用量程范围的阈值水平。
> *   **通道:**这是存储可用方法的可选参数。
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
    with image.clone() as solarize:
        # Invoke solarize function with threshold value 35
        solarize.solarize(35)
        # Save the image
        solarize.save(filename ='solarize1.jpg')
```

**输出:**

![](img/4ed3bec421ae7534c7458fa881121c28.png)

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
        # Invoke solarize function method with threshold value 60 and channel as 'green'
        pic.solarize(60, 'green')
        # Save the image
        pic.save(filename ='solarize2.jpg')
```

**输出:**

![](img/3cef9c3088b892d54e7a11cd9f967c38.png)