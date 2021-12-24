# Python 中的魔杖保存()方法

> 原文:[https://www.geeksforgeeks.org/wand-save-method-in-python/](https://www.geeksforgeeks.org/wand-save-method-in-python/)

每当我们操作一个图像并且想要保留图像以供进一步的图像时，我们使用**保存()**功能。`save()`功能将图像保存到文件或文件名中。它将最终处理过的图像保存在您的磁盘中。

> **语法:**
> 
> ```py
> # image manipulation code
> wand.image.save(file = file_object or 
>                 filename='filename.format')
> ```
> 
> **参数:**
> 它只有两个参数，一次只取一个。
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 文件 | 文件对象 | 要写入文件参数的文件对象 |
> | 文件名 | 基绳 | 要写入文件参数的 filename 对象 |

现在让我们看看保存图像的代码。

**示例#1:** 将图像保存到磁盘。

```py
# import Image from wand.image module
from wand.image import Image

# read image using 
with Image(filename ='koala.png') as img:
    # manipulate image
    img.rotate(90 * r)

    # save final image after
    img.save(filename ='final.png')
```

**输出:**

```py
In output an image named koala.png will be saved in disk
```

**例 2:**

我们也可以使用 save()函数将图像保存到输出流中。例如，以下代码将 koala.jpg.gz 图像转换为 JPEG，gzips，然后保存到 koala.jpg.gz:

```py
# import gzip
import gzip

# import Image from wand.image module
from wand.image import Image

# create gz compressed file
gz = gzip.open('koala.jpg.gz')

# read image using Image() function
with Image(filename ='pikachu.png') as img:
    # get format of image
    img.format = 'jpeg'

    # save image to output stream using save() function
    img.save(file = gz)
gz.close()
```

**输出:**

```py
A compressed file named koala.jpg.gz get saved in disk

```