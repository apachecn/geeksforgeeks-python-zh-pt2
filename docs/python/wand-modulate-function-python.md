# 魔杖调制()功能–Python

> 原文:[https://www . geesforgeks . org/wand-modulate-function-python/](https://www.geeksforgeeks.org/wand-modulate-function-python/)

**调制()**功能是 Python Wand ImageMagick 库中的一个内置功能，用于更改图像的亮度、饱和度和色调。

> **语法:**
> 
> ```
> modulate(brightness, saturation, hue)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **亮度:**该参数用于存储亮度百分比。
> *   **饱和度:**此参数用于存储饱和度百分比。
> *   **色相:**该参数用于存储色相百分比。
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
    with image.clone() as modulate:
        # Invoke modulate function with brightness 30 %, saturation 45 %, hue 25 % modulate.modulate(30, 45, 25)
        # Save the image
        modulate.save(filename ='modulate1.jpg')
```

**输出:**

![](img/3931102266c27a6916d3b3dbffaee768.png)

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
        # Invoke modulate function with  with brightness 40 %, saturation 60 %, hue 75 % pic.modulate(40, 60, 75)
        # Save the image
        pic.save(filename ='modulate2.jpg')
```

**输出:**

![](img/f89863ccb435c891f0cc192ef5010148.png)