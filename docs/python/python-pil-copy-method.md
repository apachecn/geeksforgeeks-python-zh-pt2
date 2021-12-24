# Python PIL | copy()方法

> 原文:[https://www.geeksforgeeks.org/python-pil-copy-method/](https://www.geeksforgeeks.org/python-pil-copy-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities. **PIL.Image.copy()** method copies the image to another image object, this method is useful when we need to copy the image but also retain the original.

```
Syntax:Image.copy()

Parameters: no arguments

Returns:An image object

```

```
# Importing Image module from PIL package
from PIL import Image

# creating a image object
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

# copying image to another image object
im2 = im1.copy()

# shows the copied image
im2.show()
```

**输出:**
![](img/d0cb086ecd7f6d219341c82004a2a02c.png)

```
# Importing Image module from PIL package
from PIL import Image

# creating a image object
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

# copying image to another image object
im2 = im1.copy()

# shows the original image
im1.show()
```

**输出:**
![](img/504b1728d5faab4acecc9cc4a16db9a3.png)