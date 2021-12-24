# Wand 小波 _ 去噪()函数–Python

> 原文:[https://www . geesforgeks . org/wand-小波 _ 降噪-函数-python/](https://www.geeksforgeeks.org/wand-wavelet_denoise-function-python/)

**小波去噪()**函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过应用*小波变换*来去除噪声。

> **语法:**
> 
> ```py
> wavelet_denoise(threshold, softness)
> ```
> 
> **参数:**该函数接受两个参数，如上所述，定义如下:
> 
> *   **阈值:**该参数存储平滑极限值。
> *   **柔软度:**该参数存储平滑阈值的衰减量的值..
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
    with image.clone() as wavelet_denoise:
        # Invoke wavelet_denoise function with threshold as 10
        # softness as 15
        wavelet_denoise.wavelet_denoise(10, 15)
        # Save the image
        wavelet_denoise.save(filename ='wavelet_denoise1.jpg')
```

**输出:**

![](img/9b523b62acc3af5dc13093ae6c40851f.png)

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
        # Invoke wavelet_denoise function with threshold as 20
        # softness as 10
        pic.wavelet_denoise(20, 10)
        # Save the image
        pic.save(filename ='wavelet_denoise2.jpg')
```

**输出:**

![](img/80386ba672eae5a9b7847345e6bf3af9.png)