# Python 中的 turtle.ontimer()函数

> 原文:[https://www . geesforgeks . org/turtle-ontimer-function-in-python/](https://www.geeksforgeeks.org/turtle-ontimer-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle . ontimer()

这个函数用来安装一个定时器，在 t 毫秒后调用 fun。

**语法:**

```py
turtle.ontimer(fun, t=0)

```

**参数:**

<figure class="table">

| **论据** | **描述** |
| 乐趣 | 没有参数的函数 |
| t | 一个> = 0 的数字 |

</figure>

下面是上述方法的一个示例实现:

## 蟒蛇 3

```py
# import packages
import turtle
import random

# global colors
col = ['red', 'yellow', 'green', 'blue',
       'white', 'black', 'orange', 'pink']

# method to call on timer
def fxn():
    global col
    ind = random.randint(0, 7)

    # set background color of the
    # turtle screen randomly
    sc.bgcolor(col[ind])

# set screen
sc = turtle.Screen()
sc.setup(400, 300)

# loop for timer
for i in range(10):
    turtle.ontimer(fxn, t=400*(i+1))
```

**输出:**

![](img/c58d4a11499f70e0cfc0e3bd7a1c680f.png)

这里我们可以发现，经过一段时间(由计时器设置)后，它会自动随机更改海龟图形窗口的背景颜色。