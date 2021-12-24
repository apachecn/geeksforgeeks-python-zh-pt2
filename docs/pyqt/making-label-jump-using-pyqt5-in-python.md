# 使用 Python 中的 PyQt5 进行标签跳转

> 原文:[https://www . geesforgeks . org/making-label-jump-use-pyqt 5-in-python/](https://www.geeksforgeeks.org/making-label-jump-using-pyqt5-in-python/)

#### 先决条件:[pyqt 5 简介](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/)

**PyQt5** 是跨平台的 GUI 工具包，一套针对 Qt v5 的 python 绑定。由于该库提供的工具和简单性，人们可以非常容易地开发交互式桌面应用程序。

现在，我们将看看如何让标签跳跃。在 PyQt5 中设计 2-D 游戏时，有时需要进行标签跳转，跳转标签是一个标签，当按下跳转键(这里是空格键)时，它的上升速度会降低，当它达到最大高度时，它会随着速度的增加而开始下降。由于重力作用，速度上升时下降，下降时下降。

**概念:**我们可以通过改变标签随时间的 Y 坐标来使标签跳跃，借助经典力学的基本公式，即下面给出的:
我们可以得到每次的 Y 坐标

> **力** = 1/2 *质量* velocity^2

从初始的 Y 坐标开始递减这个力值，每次都会给我们新的 Y 坐标，然后递减速度。

> #### **实施步骤:**
> 
> **1。**创建主窗口。
> T3】2。创建一个跳跃标志，以及一个速度和质量变量。
> **3** 。创建标签。
> **4。**设置标签几何图形和样式表。
> **5。**覆盖按键事件。
> **6。**在按键事件内部，检查空格键何时被按下。
> **7。**如果按下空格键，使跳转变量为真。
> T21【8】。创建一个定时器对象，并向定时器添加动作，每 50 毫秒调用一次。
> **9。**在定时器动作中获取标签的 Y 坐标，检查跳转标志是否为真。
> **10。**如果跳转标志为真，计算力，从 Y 坐标开始递减力值，并将新位置设置到标签上。
> **11。**如果速度变为零，则使质量为负，如果标签回到正常位置，则使跳转标志为假，并重置质量和速度的值。

下面是实现:

## 蟒蛇 3

```py
# importing required libraries
from PyQt5.QtWidgets import *
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import *
from PyQt5.QtCore import *

import sys

# Window class
class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # width of window
        self.w_width = 500

        # height of window
        self.w_height = 500

        # setting geometry
        self.setGeometry(100, 100, 
                         self.w_width, self.w_height)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

        # speed variable
        self.speed = 5

        self.mass = 1

        # jump flag
        self.jump = False

    # method for components
    def UiComponents(self):

        # creating a label
        self.label = QLabel(self)

        # label width
        self.l_width = 40

        # label height
        self.l_height = 40

        # setting geometry to the label
        self.label.setGeometry(200, 200, 
                               self.l_width,
                               self.l_height)

        # setting stylesheet to the label
        self.label.setStyleSheet("QLabel"
                                 "{"
                                 "border : 4px solid darkgreen;"
                                 "background : lightgreen;"
                                 "}")

        # creating a timer object
        timer = QTimer(self)

        # setting timer start time
        timer.start(50)

        # adding action to the timer
        timer.timeout.connect(self.show_time)

    # method called by the timer
    def show_time(self):

        # checking jump flag
        if self.jump:

            y = self.label.y()

            # calculate force (F). 
            # F = 1 / 2 * mass * velocity ^ 2.
            # here we are not using  ( 1/2 )
            Force = self.mass * (self.speed ** 2)

            # change in the y co-ordinate
            y -= Force

            self.label.move(200, y)

            # decreasing velocity while going up 
            # and become negative while coming down
            self.speed = self.speed - 1

            # object reached its maximum height
            if self.speed < 0:
                # negative sign is added to 
                # counter negative velocity
                self.mass = -1

            # objected reaches its original state
            if self.speed == -6:
                # making jump equal to false
                self.jump = False

                # setting original values to 
                # speed  and mass
                self.speed = 5
                self.mass = 1

    # override the key press event
    def keyPressEvent(self, event):

       # if space bar is pressed
       if event.key() == Qt.Key_Space:

           # make the jump flag true
           self.jump = True

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-435376-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200612232632/Python-2020-06-12-23-26-06.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200612232632/Python-2020-06-12-23-26-06.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200612232632/Python-2020-06-12-23-26-06.mp4)</video>