# Python 中的 turtle.filling()函数

> 原文:[https://www . geesforgeks . org/海龟-填充-python 中的函数/](https://www.geeksforgeeks.org/turtle-filling-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## 海龟.填充()

该函数用于返回填充状态(如果填充则为真，否则为假)。这不需要任何争论。

**语法:**

```py
turtle.filling()

```

下面是上述方法的实现，并附有一些例子:

**例 1:** 默认值

## python 3

```py
# import package
import turtle

# check the default 
# filling state
print(turtle.filling())
```

**输出:**

```py
False

```

**例 2:** 内补

T5】蟒 3T0T9

**输出:**

```py
True

```

**例 3:** 后补

T5】蟒 3T0T9

**输出:**

```py
False

```

在这里，我们可以检查程序中任何地方的填充状态，并且只在填充语句 ie 中得到 True 在 begin_fill()方法之后或 begin_fill()和 end_fill()方法之间。