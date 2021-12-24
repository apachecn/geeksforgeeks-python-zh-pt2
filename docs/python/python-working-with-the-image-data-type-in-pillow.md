# Python |使用枕头中的图像数据类型

> 原文:[https://www . geesforgeks . org/python-使用枕头中的图像数据类型/](https://www.geeksforgeeks.org/python-working-with-the-image-data-type-in-pillow/)

在本文中，我们将研究一个 Image 对象的一些属性，这些属性将给出有关该图像及其加载文件的信息。为此，我们需要从枕头导入图像模块。

**我们将要处理的图像:**
![](img/65905b1f6264aeeac4788c23fbb86fc5.png)

**size()方法–**它有助于获得图像的尺寸。

> img = image . open(*image _ path*)
> croppedim =*img*。size(大小)

```
# import Image module
from PIL import Image

# open the image
catIm = Image.open('D:/cat.jpg')

# Display the dimensions of the image
print(catIm.size)
```

**输出:**

```
(400, 533)
```

**分别获取高度和宽度–**它帮助我们获取图像的高度和宽度。

```
# import Image module
from PIL import Image

# Open the image
catIm = Image.open('D:/cat.jpg')

# Create two different variables 
# The first one will contain width and 
# the second one will contain height
width, height = catIm.size

# Display height and width
print(height)
print(width)
```

**输出:**

```
400
533
```

**filename()方法–**它帮助我们获取图像的文件名。

> img = image . open(*image _ path*)
> croppedim =*img*。档案名称

```
# import the Image module
from PIL import Image

# Open the image
catIm = Image.open('D:/cat.jpg')

# print the filename
print(catIm.filename)
```

**输出:**

```
D:/cat.jpg
```

**format()方法–**它帮助我们获得图像的格式。

> img = image . open(*image _ path*)
> croppedim =*img*。格式(format)

```
# import the image
from PIL import Image

# open the image
catIm = Image.open('D:/cat.jpg')

# print the format of the image
print(catIm.format)
```

**输出:**

```
JPEG
```

**format_description()方法–**它帮助我们得到图像的格式描述。

> img = image . open(*image _ path*)
> croppedim =*img*。format_description

```
# import the image
from PIL import Image

# open the image
catIm = Image.open('D:/cat.jpg')

# print the format description of the image
print(catIm.format_description)
```

**输出:**

```
JPEG (ISO 10918)
```