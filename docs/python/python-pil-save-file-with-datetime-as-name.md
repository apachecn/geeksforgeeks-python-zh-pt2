# Python PIL 以日期时间为名称保存文件

> 原文:[https://www . geesforgeks . org/python-pil-save-file-with-datetime-as-name/](https://www.geeksforgeeks.org/python-pil-save-file-with-datetime-as-name/)

在本文中，我们将看到如何使用 PIL Python 以日期时间作为名称保存图像文件。

## **所需模块:**

[**【PIL】**](https://www.geeksforgeeks.org/python-pil-image-open-method/):该库提供了广泛的文件格式支持、高效的内部表示以及相当强大的图像处理能力。

```
pip install Pillow
```

[**【日期时间】**](https://www.geeksforgeeks.org/python-datetime-module/) :这个模块帮助我们在 Python 中处理日期和时间。

```
pip install datetime
```

[**os**](https://www.geeksforgeeks.org/os-module-python-examples/) :该模块提供了一种使用操作系统相关功能的可移植方式。*os*和*os.path*模块包含许多与文件系统交互的功能。

## **分步实施:**

**步骤 1:** 使用提供的路径，使用 ***图像*** 模块打开图像。

```
img = Image.open(path)
```

**第二步:**使用[***DateTime . now()***](https://www.geeksforgeeks.org/python-now-function/)获取当前日期时间，使用**[***str time()***](https://www.geeksforgeeks.org/python-strftime-function/)格式化日期时间。**

```
curr_datetime = datetime.now().strftime('%Y-%m-%d %H-%M-%S')
```

****第三步:**使用 [***将路径分割成根和扩展。***](https://www.geeksforgeeks.org/python-os-path-basename-method/)**

```
splitted_path = os.path.splitext(picture_path)
```

****第 4 步:**在根和扩展之间添加当前日期时间，并将它们连接起来。**

```
modified_picture_path = splitted_path[0] + curr_datetime + splitted_path[1]
```

****步骤 5:** 使用 ***图像*** 模块保存修改后路径的图像。**

```
img.save(modified_picture_path)
```

**下面是完整的实现:**

## **蟒蛇 3**

```
# Import the required modules
import os
from PIL import Image
from datetime import datetime

# Main function
if __name__ == '__main__':

    picture_path = "image.jpg"

    # Open the image using image module from PIL library
    img = Image.open(picture_path)

    # Get the current date and
    # time from system
    # and use strftime function
    # to format the date and time.
    curr_datetime = datetime.now().strftime('%Y-%m-%d %H-%M-%S')

    # Split the picture path
    # into root and extension
    splitted_path = os.path.splitext(picture_path)

    # Add the current date time
    # between root and extension
    modified_picture_path = splitted_path[0] +
    curr_datetime + splitted_path[1]

    # Save the image with modified_picture_path
    img.save(modified_picture_path)
```

****输出:****

**![](img/79b5ac3d3299157d6bf090cbad039e15.png)**