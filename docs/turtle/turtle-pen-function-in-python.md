# Python 中的 turtle.pen()函数

> 原文:[https://www . geesforgeks . org/turtle-pen-function-in-python/](https://www.geeksforgeeks.org/turtle-pen-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.pen()

此功能用于在“笔字典”中返回或设置笔的属性，包括以下键/值对:

*   “显示”:真/假
*   “待定”:真/假
*   “铅笔色”:颜色字符串或颜色元组
*   “fillcolor”:颜色字符串或颜色元组
*   “冥想”:正数
*   “速度”:0 范围内的数字..10
*   “resize mode”:“auto”或“user”或“noresize”
*   “拉伸因子”:(正数，正数)
*   “剪切因子”:数字
*   【大纲】:正数
*   【倾斜】:数字

本词典可用作后续 pen()-调用的参数，以恢复前一笔状态。此外，这些属性中的一个或多个可以作为关键字参数提供。这可用于在一条语句中设置几个笔属性。

> **语法:** turtle.pen(pen=None，**pendict)
> 
> **参数:**
> 
> *   **笔:**带有下列部分或全部键的字典。
> *   ****pendict :** 一个或多个关键字参数，下面列出的关键字作为关键字。

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# import package
import turtle

# check default values
print(turtle.pen())
```

**输出:**

> { '显示':True，' pendown': True，' pencolor': 'black '，' fillcolor': 'black '，' pension ze ':1，' speed': 3，
> 'resizemode': 'noresize '，' stretchfactor': (1.0，1.0)，' shearfactor': 0.0，' outline': 1，' tilt': 0.0}

#### **例 2 :**

## 蟒蛇 3

```
# import package
import turtle

# check default to compare
print(turtle.pen())

# update with some inputs
turtle.pen(pencolor="red", outline=2)

# agian check
print(turtle.pen())
```

**输出:**

> { ' showed ':True，' pendown': True，' pencolor': 'black '，' fillcolor': 'black '，' pension ze ':1，' speed': 3，
> 'resizemode': 'noresize '，' stretchfactor': (1.0，1.0)，' shearfactor': 0.0，' outline': 1，' tilt ':' showed '，' pendown': True，' pencolor': 'red '，' fillcolor': 'black '，' pension ze ':1，' speed '，【T2 ':' resize mode ':' noresize '，' stretchfactor': (1