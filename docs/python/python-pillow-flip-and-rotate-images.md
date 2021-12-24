# 蟒蛇皮枕头–翻转和旋转图像

> 原文:[https://www . geesforgeks . org/python-抱枕-翻转-旋转-images/](https://www.geeksforgeeks.org/python-pillow-flip-and-rotate-images/)

**先决条件:** [枕头](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/)

Python 枕头或 PIL 是提供图像编辑和操作功能的 Python 库。其中的**图像**模块提供了许多翻转和旋转图像的功能。 [**image .转置()**](https://www.geeksforgeeks.org/python-pil-image-transpose-method/) 是用于旋转和翻转图像的函数，必要的关键词作为参数。

**语法:**

> image .转置(适当的关键字)

在下面给出的例子中，我们将使用一个适当的关键字来探索所有可能的旋转。

**使用的图像:**

![](img/b0a478d37ea48b39f669bc5dd49f08e7.png)

## **翻转图像**

*   **逆时针:**要逆时针翻转图像，需要传递的关键词是**图像.转置.**

**语法:**

> 转置(图像。转置)

**示例:**

## 计算机编程语言

```
from PIL import Image

img = Image.open('geek.jpg')

# flip anti-clockwise
flip_img = img.transpose(Image.TRANSPOSE)

flip_img.show()
```