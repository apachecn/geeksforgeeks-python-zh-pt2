# 魔杖边框()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-border-function-python/](https://www.geeksforgeeks.org/wand-border-function-python/)

**边框()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于应用图像周围的边框。

> **语法:**
> 
> ```
> border(color, height, width)
> ```
> 
> **参数:**该函数接受三个参数，如上所述，定义如下:
> 
> *   **颜色:**此参数用于指定颜色的值，颜色是一个字符串类型的变量。
> *   **高度:**此参数用于指定边框高度的值，边框高度为整数变量。
> *   **宽度:**此参数用于指定边框宽度的值，边框宽度是一个整数变量。
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
    with image.clone() as border:
        # Invoke border function border with color aas Green, Height as 12
        # Width as 18
        border.border('Green', int(12), int(18))
        # Save the image
        border.save(filename ='border1.jpg')
```

**输出:**

![](img/a4153b38d83ab0e089683f5f50f50aad.png)

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
        # Invoke border function with color as red, width as 10
        # Height as 10
        pic.border('Red', int(10), int(10))
        # Save the image
        pic.save(filename ='border2.jpg')
```

**输出:**

![](img/fce2adf998343ee7ebe5ede1008a8700.png)