# Python 电池\ image . getdata()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-pil-image-getdata/

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。`Image`模块提供了一个同名的类，用于表示 PIL 图像。该模块还提供了许多工厂功能，包括从文件加载图像和创建新图像的功能。

`**getdata()**`将此图像的内容作为包含像素值的序列对象返回。序列对象被展平，因此第一行的值直接跟在第 0 行的值之后，依此类推。

请注意，此方法返回的序列对象是内部 PIL 数据类型，它只支持某些序列操作。要将其转换为普通序列(例如用于打印)，请使用 list(im.getdata())。

> **语法:** Image.getdata(波段=无)
> 
> **参数**:
> 
> **波段**–返回什么波段。默认值是返回所有波段。若要返回单个波段，请传入索引值(例如，0 表示从“RGB”图像中获取“R”波段)。
> 
> **返回类型**:类似序列的对象。

**所用图像:**
![](img/e4dc81422db86e45320915b0dbc10a96.png)

```

# importing Image module from PIL package 
from PIL import Image 

# opening a  image 
im = Image.open(r"C:\Users\System-Pc\Desktop\lion.png").convert("L") 

# getting colors 
# multiband images (RBG) 
im1 = Image.Image.getdata(im) 

print(im1) 
```

**输出:**

```
ImagingCore object at 0x0000026E11CD52D0

```

**另一个例子:**这里我们换个形象。
**图像使用**
![](img/a6a62f33e59e9d685fa14fbb27737765.png)

```
# importing Image module from PIL package 
from PIL import Image 

# opening a  image 
im = Image.open(r"C:\Users\System-Pc\Desktop\tree.jpg").convert("L") 

# getting colors 
# multiband images (RBG) 
im1 = Image.Image.getdata(im) 

print(im1) 
```

**输出:**

```
ImagingCore object at 0x0000029BA596C230

```