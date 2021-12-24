# 魔杖亮度 _ 对比度()功能–Python

> 原文:[https://www . geesforgeks . org/wand-brightness _ contrast-function-python/](https://www.geeksforgeeks.org/wand-brightness_contrast-function-python/)

**brightness_contrast()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于更改图像的亮度和对比度。

> **语法:**
> 
> ```
> brightness_contrast(brightness, contrast, channel)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **亮度:**该参数用于指定介于-100 到 100 之间的亮度值。默认值为 0。
> *   **对比度:**该参数用于指定介于-100 到 100 之间的对比度值。默认值为 0。
> *   **通道:**此参数用于将图像通道的值指定为未定义、‘红色’、‘灰色’、‘青色’、‘绿色’、‘品红色’、‘蓝色’、‘黄色’、‘alpha’、‘不透明度’、‘黑色’、‘索引’、‘composite _ channels’、‘all _ channels’、‘sync _ channels’、‘default _ channels’。
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
    with image.clone() as brightness_contrast:
        # Invoke brightness_contrast function with brightness as 50, Contrast as 17
        # channel as Red
        brightness_contrast.brightness_contrast(int(50), int(17), 'Red')
        # Save the image
        brightness_contrast.save(filename ='brightness_contrast1.jpg')
```

**输出:**

![](img/95eb43ea68f2972e0e518016b31beb8e.png)

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
        # Invoke brightness_contrast function with Brightness as -44, Contrast as 33
        # Channel as Red
        pic.brightness_contrast(int(-44), int(33), 'Red')
        # Save the image
        pic.save(filename ='brightness_contrast2.jpg')
```

**输出:**

![](img/bb26a0badfc7c6bd8e4c5ccc91419718.png)