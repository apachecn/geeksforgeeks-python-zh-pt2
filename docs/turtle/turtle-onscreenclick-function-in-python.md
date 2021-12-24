# Python 中的 turtle.onscreenclick()函数

> 原文:[https://www . geesforgeks . org/turtle-onscreenclick-function-in-python/](https://www.geeksforgeeks.org/turtle-onscreenclick-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.onscreenclick()

这个函数用于将乐趣绑定到画布上的鼠标点击事件。

**语法:**

```
turtle.onscreenclick(fun, btn=1, add=None)

```

**参数:**

<figure class="table">

| **论据** | **描述** |
| 乐趣 | 带有两个参数的函数，即画布上被单击点的坐标。 |
| btn | 鼠标按钮的数量默认为 1(鼠标左键) |
| 增加 | 真或假。如果为真，将添加新绑定，否则将替换以前的绑定 |

</figure>

下面是上述方法的一个示例实现:

## 蟒蛇 3

```
# import packages
import turtle
import random

# global colors
col = ['red', 'yellow', 'green', 'blue',
       'white', 'black', 'orange', 'pink']

# method to call on screen click

def fxn(x, y):
    global col
    ind = random.randint(0, 7)

    # set screen color randomly
    sc.bgcolor(col[ind])

# set screen
sc = turtle.Screen()
sc.setup(400, 300)

# call method on screen click
turtle.onscreenclick(fxn)
```

**输出:**

![](img/224672f0b21a1ef72ab771ae07ca653d.png)

在这里我们可以发现，每当用户在屏幕上点击(箭头上的黄色点)时，它会随机改变海龟图形窗口的背景颜色。