# 魔杖拼接()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-splice-function-python/](https://www.geeksforgeeks.org/wand-splice-function-python/)

**拼接()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过在(x，y)偏移坐标处拼接一个宽 x 高的矩形来分割图像。插入的空间将被可用的背景颜色替换。

> **语法:**
> 
> ```py
> splice(width, height, x, y)
> ```
> 
> **参数:**该功能接受上述四个参数，定义如下:
> 
> *   **宽度:**此参数存储矩形的宽度。
> *   **高度:**此参数存储矩形的高度。
> *   **x:** 该参数存储 x 轴上的偏移量。
> *   **y:** 该参数存储 y 轴上的偏移量。
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
    with image.clone() as splice:
        # Invoke splice function with height as 20, width as 20, x as 10, y as 10
        splice.splice(20, 20, 10, 10)
        # Save the image
        splice.save(filename ='splice1.jpg')
```

**输出:**

![](img/a6b8f9b8af7e263764c0f66bbf78ea9c.png)

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
        # Invoke splice function with height as 10, width as 10, x as 15, y as 20
        pic.splice(10, 10, 15, 20)
        # Save the image 
        pic.save(filename ='splice2.jpg')
```

**输出:**

![](img/8399358775f1cbd5d9a49e6142cd0332.png)