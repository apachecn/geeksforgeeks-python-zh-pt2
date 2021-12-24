# 蟒蛇棒–概述

> 原文:[https://www.geeksforgeeks.org/python-wand-an-overview/](https://www.geeksforgeeks.org/python-wand-an-overview/)

**魔杖**是一个 python 的 Imagick 库。它支持 Python 2.6、2.7、3.3+和 PyPy 中 Imagick API 的功能。该库不仅有助于处理图像，还为使用 NumPy 的机器学习代码提供了有价值的功能。

**安装:**
**由皮普:**

```py
**$** pip install Wand
```

由于魔杖是一个 Imagick API，所以我们需要 Imagick 依赖项。

**Imagick 的安装:**

*   **适用于 Ubuntu/Debian:**

    ```py
    **$** sudo apt-get install libmagickwand-dev
    ```

*   **For Mac (By Brew Installer)**

    ```py
    **$** brew install imagemagick
    ```

    **安装电脑端口**

    ```py
    **$** sudo port install imagemagick
    ```

    **注意:**如果 Python 没有使用 MacPorts 安装，我们需要导出 MAGICK_HOME。

    ```py
    **$** export MAGICK_HOME=/opt/local
    ```

    **Example 1: Reading an Image:*****Input Image:*** geeksforgeeks.png![geeksforgeeks](img/e7e47360b64ac26b3962b0da3bec1fef.png)

    ```py
    # Import library from the wand
    from wand.image import Image

    # Import the image
    with Image(filename ='geeksforgeeks.png') as pic:

        # Read the image to fetch actual dimensions
        print('Width of the image:', pic.width)
        print('Height of the image:', pic.height)
    ```

    **输出:**

    ```py
    ('Width of the image:', 667L)
    ('Height of the image:', 184L)

    ```

    **示例 2:模糊图像:**

    ```py
    # Import library from the wand 
    from wand.image import Image

    # Import the image
    with Image(filename ="geeksforgeeks.png") as pic:

        # Invoke blur function with radius 0 and sigma 3
        pic.blur(radius = 0, sigma = 3)

        # save the processed iamge
        pic.save(filename ="blur1.png")
    ```

    **输出:**
    ![blur-geeksforgeeks-pyhton](img/c1f90e616a54447109ae9500b2906ca0.png)

    **示例 3:转换图像**

    ```py
    # Import library from the wand
    from wand.image import Image

    # Import the image
    with Image(filename ='geeksforgeeks.png') as image:
        # Clone the image in order to process
        with image.clone() as flip:

            # Invoke flip function
            flip.flip()

            # Save the image
            flip.save(filename ='flip-geeksforgeeks.jpg')
    ```

    **输出:**
    ![flip-geeksforgeeks](img/6d2666efe3496c862291ffa0ff147ec0.png)

    **例 4:图纸:**

    ```py
    # Import libraries from the wand  
    from wand.image import Image
    from wand.drawing import Drawing
    from wand.color import Color

    with Drawing() as draw:
        # Set Stroke color the circle to black
        draw.stroke_color = Color('black')

        # Set Width of the circlw to 2 
        draw.stroke_width = 2

        # Set the fill color to 'White (# FFFFFF)'
        draw.fill_color = Color('white')

        # Invoke Circle function with center 
        # at 200, 200 and radius 100
        draw.circle((200, 200), # Center point
                    (100, 100)) # Perimeter point
        with Image(width = 400, height = 400, 
                  background = Color('lightgreen')) as pic:
            draw(pic)
            pic.save(filename ='circle1.jpg')
    ```

    **输出:**
    ![circle](img/a7f7fbebdf839185ac00a28b3a95c683.png)
    **参考文献:**

    *   [http://docs.wand-py.org/en/0.5.9/index.html](http://docs.wand-py.org/en/0.5.9/index.html)