# Python–海龟. exit tonclick()

> 原文:[https://www.geeksforgeeks.org/python-turtle-exitonclick/](https://www.geeksforgeeks.org/python-turtle-exitonclick/)

海龟模块以面向对象和面向过程的方式提供海龟图形原语。因为它使用 tkinter 作为底层图形，所以需要安装一个支持 Tk 的 Python 版本。

## turtle.exitonclick():

该功能用于进入主循环，直到鼠标被点击。这不需要任何争论。将`bye()`方法绑定到鼠标点击标题屏幕。如果`using_IDLE` –配置字典中的值为假(默认值)，则进入主循环。如果使用了带有-n 开关的 IDLE(没有子进程)，这个值应该在 turtle.cfg 中设置为 True。在这种情况下，对于客户端脚本，IDLE 的 mainloop 也是活动的。

这是 Screen 类的一种方法，不适用于 TurtleScreen 实例。

> **语法:**海龟. exittoncick()
> T3】参数:无
> T6】返回:无

下面是上述方法的一个实现示例:

**示例:**

```py
# import package
import turtle

# loop for motion
for i in range(3):
  turtle.circle(40)
  turtle.right(120)

# exit from the screen 
# if and only if
# mouse is clicked
turtle.exitonclick()
```

**输出:**
![](img/684eccba05b83d924352f342ffa658e4.png)

这里我们可以看到:

*   龟屏已加载
*   乌龟画了一些东西
*   龟窗保持原样
*   当用户点击海龟窗口(黄色标志)时，海龟窗口关闭，即:点击退出。