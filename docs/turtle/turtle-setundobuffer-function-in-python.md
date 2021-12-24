# Python 中的 turtle.setundobuffer()函数

> 原文:[https://www . geeksforgeeks . org/turtle-setundo buffer-function-in-python/](https://www.geeksforgeeks.org/turtle-setundobuffer-function-in-python/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 Tkinter 作为底层图形，所以它需要安装一个支持 Tk 的 Python 版本。

## turtle . setundobuffer()

该功能用于设置或禁用 undobuffer。它接受大小参数。如果大小是整数，则安装给定大小的空撤销缓冲区。Size 给出了可由 undo()函数撤消的海龟动作的最大数量。如果大小为“无”，则不存在撤销缓冲区。

**语法:**

```
turtle.setundobuffer(size)
```

下面是上述方法的实现，并附有一些例子:

**例**T2【1:

## 蟒蛇 3

```
# importing package
import turtle

# check default value of undobuffer
print(turtle.undobufferentries())

# set undo buffer by 10 as value
turtle.setundobuffer(10)

# loop executes 50 times with
# turtle.forward(1) statement
# i.e; undobufferentries gives 50
for i in range(50):
      turtle.forward(1)

# but gives 10 as it is set already
print(turtle.undobufferentries())
```

**输出:**

```
0
10
```

**例 2 :**

## 蟒蛇 3

```
# importing package
import turtle

# print default value
print(turtle.undobufferentries())

# loop for motion
for i in range(50):

    # one statement increase the
    # undobuffer entries
    turtle.fd(1)

# print undobuffer entries ie; 50
# due to above loop with one statement
print(turtle.undobufferentries())

# set undobuffer to None
turtle.setundobuffer(None)

# print undobuffer entries
# i.e; value set by set undobuffer
print(turtle.undobufferentries())
```

**输出:**

```
0
50
0
```