# Python 中的 turtle.write()函数

> 原文:[https://www . geesforgeks . org/turtle-write-function-in-python/](https://www.geeksforgeeks.org/turtle-write-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.write()

该函数用于在当前海龟位置书写文本。

**语法:**

> turtle.write(arg，move=False，align='left '，font=('Arial '，8，' normal'))

**参数:**

<figure class="table">

| **论据** | **描述** |
| 银 | 信息，将被写入到标题屏幕 |
| 移动 | 真/假 |
| 排列 | “左”、“中”或“右”弦之一 |
| 字体 | 元组(fontname、fontsize、fonttype) |

</figure>

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```py
# import package
import turtle

# write text
turtle.write("GeeksForGeeks")
```

**输出:**

![](img/74e5e014cbab7fc423e33dfdc74337fc.png)

**例 2 :**

## 蟒蛇 3

```py
# import package
import turtle

# write text
# move turtle
turtle.write("GeeksForGeeks", move=True)
```

**输出:**

![](img/7d24f7f55b68798610e3f07fb6100daa.png)

**例 3 :**

## 蟒蛇 3

```py
# import package
import turtle

# write text
# styling font
turtle.write("GeeksForGeeks", font=("Verdana",
                                    15, "normal"))
```

**输出:**

![](img/439c54a055138d968770a109643ed0e3.png)

**例 4 :**

## 蟒蛇 3

```py
# import package
import turtle

# write text
# align at right
turtle.write("GeeksForGeeks", align="right")
```

**输出:**

![](img/64a40808f1e2c11f904e0287497ccb26.png)