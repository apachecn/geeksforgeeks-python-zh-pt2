# 用 Python 读取图像

> 原文:[https://www.geeksforgeeks.org/reading-images-in-python/](https://www.geeksforgeeks.org/reading-images-in-python/)

在图像处理方面，Python 支持非常强大的工具。让我们看看如何使用不同的库来处理图像，如 [OpenCV](http://gdevtest.geeksforgeeks.org/reading-image-opencv-using-python/) 、 [Matplotlib](https://www.geeksforgeeks.org/reading-image-opencv-using-python/) 、 [PIL](https://www.geeksforgeeks.org/working-images-python/) 等。

1.  **Using OpenCV :** OpenCV (Open Source Computer Vision) is a computer vision library that contains various functions to perform operations on pictures or videos. It was originally developed by Intel but was later maintained by Willow Garage and is now maintained by Itseez. This library is cross-platform that is it is available on multiple programming languages such as Python, C++ etc.

    ```
    # Python program to read image using OpenCV

    # importing OpenCV(cv2) module
    import cv2

    # Save image in set directory
    # Read RGB image
    img = cv2.imread('g4g.png') 

    # Output img with window name as 'image'
    cv2.imshow('image', img) 

    # Maintain output window utill
    # user presses a key
    cv2.waitKey(0)        

    # Destroying present windows on screen
    cv2.destroyAllWindows() 
    ```

    **输出:**

    ![](img/4ba3bd8fa9a5e6d9e37b6f2a5eebcf54.png)

2.  **Using MatplotLib :** Matplotlib is an amazing visualization library in Python for 2D plots of arrays. Matplotlib is a multi-platform data visualization library built on NumPy arrays and designed to work with the broader SciPy stack. It was introduced by John Hunter in the year 2002\. Matplotlib comes with a wide variety of plots. Plots helps to understand trends, patterns, and to make correlations. They’re typically instruments for reasoning about quantitative information.

    ```
    # Python program to read 
    # image using matplotlib

    # importing matplotlib modules
    import matplotlib.image as mpimg
    import matplotlib.pyplot as plt

    # Read Images
    img = mpimg.imread('g4g.png')

    # Output Images
    plt.imshow(img)
    ```

    **输出:**

    ![](img/af7bf76276a6b2294e658c2dde433570.png)

3.  **Using PIL :** PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. It was developed by Fredrik Lundh and several other contributors. Pillow is the friendly PIL fork and an easy to use library developed by Alex Clark and other contributors.

    ```
    # Python program to read
    # image using PIL module

    # importing PIL
    from PIL import Image

    # Read image
    img = Image.open('g4g.png')

    # Output Images
    img.show()

    # prints format of image
    print(img.format)

    # prints mode of image
    print(img.mode)
    ```

    **输出:**

    ```

    PNG
    RGBA

    ```