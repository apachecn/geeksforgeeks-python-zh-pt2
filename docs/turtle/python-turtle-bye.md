# 蟒蛇–乌龟拜拜()

> 原文:[https://www.geeksforgeeks.org/python-turtle-bye/](https://www.geeksforgeeks.org/python-turtle-bye/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 tkinter 作为底层图形，所以需要安装一个支持 Tk 的 Python 版本。

## 乌龟.再见()

该功能用于关闭海龟图形窗口。这不需要任何争论。

> **语法:**龟拜拜()
> T3】参数:无
> T6】返回:无

下面是上述方法的实现，并附有一些例子:

**例 1:**

```
# import package
import turtle 

# set turtle speed to 
# slowest for better
# understandings

turtle.speed(1)
# motion

turtle.forward(200)
# use bye() method to 
# shut the window
turtle.bye()
```

**输出:**
![](img/bc7b8f8f624be468f7e23b51336c4d9d.png)

**例 2 :**

```
# import package
import turtle 

# set drawing turtle speed
turtle.speed(10)

# loop for pattern
for i in range(12):
  turtle.circle(50)
  turtle.right(30)

# As simply use of bye() here will shut the 
# turtle graphics window too fast so use 
# loops to pass the time
for i in range(2000):
  for j in range(500):
    pass

# shut the turtle graphics window
turtle.bye()
```

**输出:**
![](img/4b9b1c376a9d293445861c52e7c01ea7.png)