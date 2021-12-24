# 魔杖–创建带有背景的空图像

> 原文:[https://www . geesforgeks . org/wand-create-empty-image-with-background/](https://www.geeksforgeeks.org/wand-create-empty-image-with-background/)

在 Python 中，我们可以使用魔杖创建实心背景。我们可以使用这些背景在图像中进一步使用。我们可以在无背景图像中使用这些背景，使其更具吸引力。这可以通过简单地使用 Image()函数并设置宽度、高度和背景参数来完成。
**语法:**

## 蟒蛇 3

```
with Image(width=<i>image_width </i>,
           height=<i>image_height </i>,
           background ='color') as img:

# other image manipulation code
```

现在让我们看看创建背景的代码。
**例 1:**

## 蟒蛇 3

```
# import Image from wand.image module
from wand.image import Image

# create image using Image() function
with Image(width = 400, height = 300) as img:

    # Save image with a valid filename
    img.save(filename ='transparent.png')
```

**输出:**

![](img/ead6c652ca0bd25ad73a8606462abeca.png)

**示例 2:** 用纯绿色创建背景

## 蟒蛇 3

```
# import Color from wand.color module
from wand.color import Color
# import Image from wand.image module
from wand.image import Image

clr = Color('green')
with Image(width = 400, height = 300, background = clr) as img:
    img.save(filename ='green.png')
```

**输出:**

![](img/0f32b6d4764be561fee1f1f253e099d7.png)