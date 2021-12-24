# 魔杖自适应 _ 模糊()功能–Python

> 原文:[https://www . geeksforgeeks . org/wand-adaptive _ blur-function-python/](https://www.geeksforgeeks.org/wand-adaptive_blur-function-python/)

**adaptive_blur()** 函数是 Python Wand ImageMagick 库中的一个内置函数，用于通过递减高斯值作为运算符来模糊图像。它出现在课堂上*魔杖图像*。

> **语法:**
> 
> ```py
> adaptive_blur(radius, sigma, channel)
> ```
> 
> **参数:**该功能接受三个参数，如上所述，定义如下:
> 
> *   **半径:**此参数用于指定半径值，即高斯孔径的大小。
> *   **σ:**此参数用于指定σ的值，即高斯滤波器的标准偏差。
> *   **通道:**此参数用于将图像通道的值指定为未定义、‘红色’、‘灰色’、‘青色’、‘绿色’、‘品红色’、‘蓝色’、‘黄色’、‘alpha’、‘不透明度’、‘黑色’、‘索引’、‘composite _ channels’、‘all _ channels’、‘sync _ channels’、‘default _ channels’。
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
    with image.clone() as adaptive_blur:
        # Invoke adaptive_blur function with radius as 2, sigma as
        # 3 and channel as Green
        adaptive_blur.adaptive_blur(0, 3, 'Green')
        # Save the image
        adaptive_blur.save(filename ='adaptive_blur1.jpg')
```

**输出:**

![](img/9f32558f43604484acd4a70c0bfb3a25.png)

**例 2:**

## 蟒蛇 3

```py
# Import library from Image
from wand.image import Image

# Import the image
with Image(filename ='../geeksforgeeks.png') as image:

    # Clone the image in order to process
    with image.clone() as adaptive_blur:
        # Invoke adaptive_blur function with radius as 2, sigma as
        # 3 and channel as Green
        adaptive_blur.adaptive_blur(int(0), int(3), 'Green')

        # Save the image
        adaptive_blur.save(filename ='adaptive_blur1.jpg')
```

**输出:**

![](img/7885da181db934b34c9958e63d394b68.png)