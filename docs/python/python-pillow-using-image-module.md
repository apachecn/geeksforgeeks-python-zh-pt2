# 蟒蛇枕–使用图像模块

> 原文:[https://www . geesforgeks . org/python-枕头使用-图像-模块/](https://www.geeksforgeeks.org/python-pillow-using-image-module/)

在本文中，我们将看到如何使用 Python 中的 PIL 图像模块。首先，让我们看看如何安装 PIL。

### **安装:**

**Linux:** 在 Linux 终端上键入以下内容:

```py
pip install Pillow
```

通过终端安装 pip:

```py
sudo apt-get update
sudo apt-get install python-pip
```

### 使用图像模块

在这里，我们将介绍图像模块提供的一些方法和属性，如下所示:

*   打开图像，
*   保存图像，
*   图像的大小，
*   旋转图像，
*   裁剪图像，
*   调整图像大小等等。

让我们借助一些例子来逐一讨论这个问题。

#### **1。打开图像:**

要使用 PIL 打开图像，我们使用 open()方法。

> **语法:** PIL。Image.open(fp，模式='r '，格式=无)

## 蟒蛇 3

```py
# importing Image from PIL
from PIL import Image

# open an image
img = Image.open('gfg.png')
```

**输出:**

![](img/2307b4097a9d2983120a4931023c1fc7.png)

#### **2。检索**图像的**大小:**

为了检索图像的大小，我们将使用图像对象提供的属性，即；Image.size 属性。

> **语法:**图像大小

## 蟒蛇 3

```py
from PIL import Image

with Image.open("gfg.png") as image:
    width, height = image.size

print((width,height))
```

**输出:**

```py
(200, 200)
```

#### 3.保存图像中的更改:

为了保存图像，我们使用了 Image.save()方法。

> **语法:** Image.save(fp，格式=无，* *参数)
> 
> **参数:**
> 
> *   **FP**–文件名(字符串)，路径名。路径对象或文件对象。
> *   **格式**–可选格式覆盖。如果省略，使用的格式由文件扩展名决定。如果使用文件对象而不是文件名，则应始终使用此参数。
> *   **选项**–图像写入器的额外参数。
> 
> **返回:**无

## 蟒蛇 3

```py
from PIL import Image

img = Image.open("gfg.png")

img.save("logo.jpg")
```

**输出:**

![](img/3b2efdef8e18627157fd1548e97be9dc.png)

#### **4。旋转图像:**

图像旋转需要一个角度作为参数来旋转图像。

> **语法:**图像。旋转(角度，重采样=0，展开=0，中心=无，平移=无，填充颜色=无)
> 
> **参数:**
> 
> *   **角度**–逆时针角度。
> *   **重采样**–可选的重采样过滤器。
> *   **展开**–可选展开标志。如果为真，则扩展输出图像，使其足够大以容纳整个旋转图像。
> *   **中心**–可选旋转中心(二元组)。原点在左上角。默认是图像的中心。
> *   **平移**–可选的旋转后平移(二元组)。
> *   **填充颜色**–旋转图像外部区域的可选颜色。

## 蟒蛇 3

```py
from PIL import Image

img = Image.open("gfg.png")

rot_img = img.rotate(180)

rot_img.save("rotated_gfg.png")
```

**输出:**

![](img/2307b4097a9d2983120a4931023c1fc7.png)

原象

![](img/a3544e20af485a705e8fb373d1354128.png)

旋转图像

#### **5。**裁剪**图像:**

Image.crop(框)采用一个 4 元组(左、上、右、下)像素坐标，并从使用过的图像中返回一个矩形区域。

> **语法:** PIL。图像.裁剪(框=无)
> 
> **参数:**
> 
> *   box–定义左、上、右和下像素坐标的 4 元组。
> 
> **返回类型:**图像(以(左、上、右、下)元组形式返回矩形区域)。
> 
> **返回:**一个图像对象。

## 蟒蛇 3

```py
from PIL import Image

#  open image and get size
img = Image.open("gfg.jpg")
width, height = img.size

# cropped image using coordinates
area = (0, 0, width/2, height/2)
crop_img = img.crop(area)
crop_img.save("cropped_image.jpg")
```

**输出:**

![](img/952101eb5595caddddd17548722c19ec.png)

裁剪图像

#### **6。调整图像大小:**

Image.resize(大小)用于调整大小。这里，大小是以 2 元组的宽度和高度提供的。

> **语法:** Image.resize(大小，重采样=0)
> 
> **参数:**
> 
> *   **大小**–以像素为单位的请求大小，为二元组:(宽度，高度)。
> *   **重采样**–可选的重采样过滤器。这可能是 PIL 的一个。图片。最近的(使用最近的邻居)，PIL。图像。双线性(线性插值)，PIL。双三次样条插值，或 PIL。Image.LANCZOS(高质量下采样滤波器)。如果省略，或者如果图像具有模式“1”或“P”，则设置为 pil . image . nearless
> 
> **返回类型:**一个图像对象。

## 蟒蛇 3

```py
from PIL import Image

img = Image.open("gfg.png")
width, height = img.size

#resizing the image 
img = img.resize((width//2, height//2))

img.save("resized_picture.png")
```

**输出:**

![](img/3b2efdef8e18627157fd1548e97be9dc.png)

调整图像大小

#### **7。将图像粘贴到另一个图像上:**

第二个参数可以是 2 元组(指定左上角)，也可以是 4 元组(左、上、右、下)–在这种情况下，粘贴图像的大小必须与此框区域的大小匹配，或者等于(0，0)的“无”。

> **语法:** PIL。图像。图像。粘贴(图像 _1，图像 _2，框=无，遮罩=无)
> 
> 运筹学
> 
> 图像 _ 对象.粘贴(图像 _2，框=无，遮罩=无)
> 
> **参数:**
> 
> *   **image_1/image_object :** 是要粘贴其他图像的图像。
> *   **image_2** :源图像或像素值(整数或元组)。
> *   **框** ***:*** 一个可选的 4 元组，给出要粘贴的区域。如果改为使用二元组，它将被视为左上角。如果省略或无，源将粘贴到左上角。
> *   **蒙版**:可选的蒙版图像。
> 
> 如果给定图像作为第二个参数，并且没有第三个参数，则该框默认为(0，0)，第二个参数被解释为蒙版图像。

## 蟒蛇 3

```py
from PIL import Image

img1 = Image.open("gfg.jpg")

#pasting img2 on img1
img2 = Image.open("gfg.png")
img1.paste(img2, (50, 50))

img1.save("pasted_picture.jpg")
```

**输出:**

![](img/f9c383854fb0b1c0f9bab72cc5998b86.png)

#### **8。变换图像:**

这个特征给我们一个镜像

> **语法:**转置图像(以 90 度步进翻转或旋转)
> 
> **参数:**
> 
> *   **法**–PIL 之一。图像。翻转 _ 左 _ 右，PIL。图像。翻转 _ 顶部 _ 底部，PIL。图像。旋转 90 度，PIL。图像。旋转 180 度，PIL。Image.ROTATE_270 或 PIL.Image .转置
> 
> **返回类型:**一个图像对象。

## 蟒蛇 3

```py
from PIL import Image

img = Image.open("gfg.png")     

#flipping the image by 180 degree horizontally
transposed_img = img.transpose(Image.FLIP_LEFT_RIGHT)

transposed_img.save("transposed.png")
```

**输出:**

![](img/51d5b71ebcefb3137ce7d69a1398834c.png)

原创

![](img/78e366e7371e015009c98e93c2e643cc.png)

换位图像

#### **9。创建缩略图:**

此方法创建打开的图像的缩略图。它不返回新的图像对象，而是对当前打开的图像对象本身进行就地修改。如果不想更改原始图像对象，请创建一个副本，然后应用此方法。此方法还根据传递的大小评估保持图像纵横比的适当性。

> **语法:** Image.thumbnail(大小，重采样=3)
> 
> **参数:**
> 
> *   **尺寸**–要求的尺寸。
> *   **重采样**–可选重采样过滤器。
> 
> **返回类型:**一个图像对象。

## 蟒蛇 3

```py
from PIL import Image

img = Image.open("gfg.png")

img.thumbnail((200, 200))

img.save("thumb.png")
```

**输出:**

![](img/a3544e20af485a705e8fb373d1354128.png)

200 x 200 像素的缩略图