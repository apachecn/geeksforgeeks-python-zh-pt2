# 魔杖旋转()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-rotate-function-python/](https://www.geeksforgeeks.org/wand-rotate-function-python/)

**rotate()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于向右旋转图像。它采用旋转不可用的背景色。

> **语法:**
> 
> ```
> rotate(degree, background, reset_coords)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **度数:**该参数存储旋转度数。
> *   **背景:**该参数存储没有可用旋转部分的部分的背景颜色..
> *   **reset_coords:** 这是一个布尔参数，表示旋转后，坐标框将被重新定位到新图像的左上角。默认情况下为真。
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
    with image.clone() as rotate:
        # Invoke rotate function
        rotate.rotate(45, 'red', True)
        # Save the image
        rotate.save(filename ='rotate1.jpg')
```

**输出:**

![](img/4990d9e54c66c43387fd539f86664e79.png)

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
        # Invoke rotate function method
        pic.rotate(50, 'Green', False)
        # Save the image
        pic.save(filename ='rotate2.jpg')
```

**输出:**

![](img/0937797b825c84d74d5fee980b01eb6a.png)