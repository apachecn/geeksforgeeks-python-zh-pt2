# 魔杖阴影()功能–Python

> 原文:[https://www.geeksforgeeks.org/wand-shade-function-python/](https://www.geeksforgeeks.org/wand-shade-function-python/)

**shade()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过模拟高角度的光线来生成和创建 3D 效果。

> **语法:**
> 
> 阴影(灰色、方位角、仰角)
> 
> **参数:**该函数接受三个参数，如上所述，定义如下:
> 
> *   **灰色:**这是一个存储隔离效果的布尔参数。默认值为“假”。
> *   **方位角:**该参数存储与 x 轴的角度。
> *   **高程:**此参数存储与 z 轴的角度量。
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
    with image.clone() as shade:
        # Invoke shade function
        shade.shade(True, 10, 15)
        # Save the image
        shade.save(filename ='shade1.jpg')
```

**输出:**

![](img/849fc1ed39d031a99dc026b319537276.png)

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
        # Invoke shade function method
        pic.shade(False, 15, 15)
        # Save the image
        pic.save(filename ='shade2.jpg')
```

**输出:**

![](img/f824d27af6d140d34783c044f2ce26b9.png)