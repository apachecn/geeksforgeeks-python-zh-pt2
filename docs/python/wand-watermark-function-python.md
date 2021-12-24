# 魔杖水印()功能–Python

> 原文:[https://www . geesforgeks . org/wand-watermark-function-python/](https://www.geeksforgeeks.org/wand-watermark-function-python/)

**水印()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于将提供的图像透明化，并将其放置在当前图像上，图像的左上角位于坐标左侧，当前图像的顶部。

> **语法:**
> 
> ```py
> watermark(image, transparency, left, top)
> ```
> 
> **参数:**该函数接受上面提到的四个参数，定义如下:
> 
> *   **图像:**该参数存储将要放置的图像。
> *   **透明度:**该参数存储透明度的数值。范围从 0.0 到 1.0。
> *   **左:**此参数存储图像将被放置的 x 坐标的值。
> *   **顶部:**该参数存储图像将被放置的 y 坐标的值。
> 
> **返回值:**该函数返回魔杖图像图像对象。

**原图:**

![](img/2d3a0fdbc25c0bbb46c47454d1b0acc7.png)

**水印图像:**

![](img/9e1274fc17585762f2264082e8c19a42.png)

**例 1:**

## 蟒蛇 3

```py
# Import library from Image
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:
    # Import the watermark image
    with Image(filename ='wave1.jpg') as water:
        # Clone the image in order to process
        with image.clone() as watermark:
            # Invoke watermark function with watermark image, transparency as 0.5
            # left as 10 and top as 20
            watermark.watermark(water, 0.5, 10, 20)
                # Save the image
            watermark.save(filename ='watermark1.jpg')
```

**输出:**

![](img/2fa7de1ff8582fe1ffc3cc5af86f4fe1.png)

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
        # Import the watermark image
        with Image(filename ='wave1.jpg') as water:
            # Invoke watermark function with watermark image, transparency as 0.5
            # left as 10 and top as 20
            pic.watermark(water, 0.5, 10, 20)
            # Save the image
            pic.save(filename ='watermark2.jpg')
```

**输出:**

![](img/6319f733971240669dd9d5b035987b9d.png)