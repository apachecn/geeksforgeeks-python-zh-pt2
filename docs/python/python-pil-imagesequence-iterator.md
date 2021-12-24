# Python PIL |图像序列。迭代器()

> 原文:[https://www . geesforgeks . org/python-pil-imagesequence-iterator/](https://www.geeksforgeeks.org/python-pil-imagesequence-iterator/)

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。 **`ImageSequence`** 模块包含一个包装类，允许你迭代一个图像序列的帧。

`**ImageSequence.Iterator()**`这个类实现了一个迭代器对象，可以用来循环一个图像序列。您可以使用[ ]运算符通过索引来访问元素。如果您试图访问不存在的帧，此运算符将引发索引错误。

> **语法:** PIL。迭代器
> 
> **参数:**
> **im**–一个图像对象。
> 
> **返回:**一个图像对象。

**所用图像:**
![](img/b9d9345df71fc8e6c101def0e1afd214.png)

```py

# importing Image class from PIL package 
from PIL import Image, ImageSequence

# creating a object 
im = Image.open(r"C:\Users\System-Pc\Desktop\home.png")
index = 1
for frame in ImageSequence.Iterator(im):
    frame.save("frame % d.png" % index)
    index = index + 1

im.getdata()
im.show()
```

**输出:**
![](img/19b3c0139b6138f2b179df0507a4e55f.png)

**另一个例子:**这里我们使用另一个图像。jpg 扩展名。

**所用图像:**
![](img/d2608681f1435d89fc11f18e4eb640ad.png)

```py

# importing Image class from PIL package 
from PIL import Image, ImageSequence

# creating a object 
im = Image.open(r"C:\Users\System-Pc\Desktop\tree.jpg")
index = 1
for frame in ImageSequence.Iterator(im):
    frame.save("frame % d.jpg" % index)
    index = index + 1

im.getdata()
im.show()
```

**输出:**
![](img/d2608681f1435d89fc11f18e4eb640ad.png)