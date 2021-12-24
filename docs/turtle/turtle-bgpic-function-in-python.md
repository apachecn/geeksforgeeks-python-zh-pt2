# Python 中的 turtle.bgpic()函数

> 原文:[https://www . geesforgeks . org/turtle-bgpic-function-in-python/](https://www.geeksforgeeks.org/turtle-bgpic-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle.bgpic()

此功能用于设置背景图像或返回当前背景图像的名称。它只需要一个参数“picname”。该参数可以通过以下不同方式使用:

*   如果 picname 是文件名，则将相应的图像设置为背景。
*   如果 picname 为“nopic”，删除背景图像(如果存在)。
*   如果 picname 为无，则返回当前背景图像的文件名。

**语法:**

```
turtle.bgpic(picname=None)

```

下面是上述方法的实现，并附有一些例子:

**例 1 :**

## 蟒蛇 3

```
# import package
import turtle

# check background image
print(turtle.bgpic())
```

**输出:**

```
nopic

```

**例 2 :**

## 蟒蛇 3

```
# import package
import turtle

# set background image
turtle.bgpic("gfg.png")
```

**输出:**

![](img/b6188c50c3b240869fa948387cba59f2.png)

**例 3 :**

## 蟒蛇 3

```
# import package
import turtle

# set background image
turtle.bgpic("gfg.png")

# loop for motion
for i in range(20):
    turtle.forward(5+5*i)
    turtle.right(90)

# delete background image
turtle.bgpic("nopic")
```

**输出:**

![](img/5921d61842ea16a4351887cb56ee0103.png)