# 魔杖求反()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-negate-function-python/](https://www.geeksforgeeks.org/wand-negate-function-python/)

**求反()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于求反参考图像中的颜色。

> **语法:**
> 
> ```py
> negate(grayscale, channel)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **灰度:**这是一个布尔参数，它存储了否定图像中灰度像素的状态。
> *   **通道:**该参数将通道类型存储为‘绿色’、‘红色’、‘黄色’等。
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
    with image.clone() as negate:
        # Invoke negate function with Channel "green"
        negate.negate(True, "green")
        # Save the image
        negate.save(filename ='negate1.jpg')
```

**输出:**

![](img/d3d6ffca1de7937a56129503f56dae1a.png)

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
        # Invoke negate function with channel "yellow"
        pic.negate(False, "yellow")
        # Save the image
        pic.save(filename ='negate2.jpg')
```

**输出:**

![](img/999f4deadbf9eb8b6de4c73eddaa39e6.png)