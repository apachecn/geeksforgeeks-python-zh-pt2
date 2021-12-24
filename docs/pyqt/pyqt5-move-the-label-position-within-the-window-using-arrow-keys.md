# PyQt5–使用箭头键

在窗口内移动标签位置

> 原文:[https://www . geeksforgeeks . org/pyqt 5-使用箭头键移动窗口内的标签位置/](https://www.geeksforgeeks.org/pyqt5-move-the-label-position-within-the-window-using-arrow-keys/)

在本文中，我们将看到如何使用箭头键在窗口中移动标签，即当箭头键(方向键)被按下时，它会向那个方向移动。例如，当用户按下向上箭头键时，标签将向上移动，类似于其他箭头键，标签也将改变其位置。

**概念:**我们可以通过增加/减少标签的坐标值来改变标签的位置，但是如果它到达侧面的任何一端，则不增加或减少。下面是按下每个箭头键时要做的数据。

```
When Up arrow key is pressed : X Co-ordinate remain same, decrement the Y Co-ordinate 
When Down arrow key is pressed : X Co-ordinate remain same, increment the Y Co-ordinate 
When Left arrow key is pressed : Decrement X Co-ordinate, Y Co-ordinate remain same
When Right arrow key is pressed : Increment X Co-ordinate, Y Co-ordinate remain same

```

下面是边缘限制数据，因此标签应该保留在窗口中

> 对于顶部边缘，y 坐标应始终大于 0
> 对于底部边缘，y 坐标应始终小于窗口高度–标签高度
> 对于左侧边缘，x 坐标应始终大于 0
> 对于右侧边缘，x 坐标应始终小于窗口宽度–标签宽度

> 实施步骤:
> 1。创建主窗口
> 2。在主窗口
> 3 内创建标签。将样式表几何图形添加到标签
> 4。创建速度变量
> 5。超越按键事件
> 6。在按键事件中获取标签的当前 x 和 y 坐标
> 7。检查按下了哪个键，如果没有到达侧端，则借助`move`方法，通过增加/减少速度值来更新 x 和 y 坐标

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

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
        self.setGeometry(100, 100, self.w_width, self.w_height)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

        # speed variable
        self.speed = 15

    # method for components
    def UiComponents(self):

        # creating a label
        self.label = QLabel(self)

        # label width
        self.l_width = 40

        # label height
        self.l_height = 40

        # setting geometry to the label
        self.label.setGeometry(200, 200, self.l_width, self.l_height)

        # setting stylesheet to the label
        self.label.setStyleSheet("QLabel"
                                 "{"
                                 "border : 4px solid darkgreen;"
                                 "background : lightgreen;"
                                 "}")

    # override the key press event
    def keyPressEvent(self, event):

        # get the current co-ordinates of the label
        # X Co-ordinate
        x = self.label.x()

        # Y Co-ordinate
        y = self.label.y()

        # if up arrow key is pressed
        if event.key() == Qt.Key_Up:

            # if top position is attained
            if y > 0:
                self.label.move(x, y - self.speed)

        # if down arrow key is pressed
        elif event.key() == Qt.Key_Down:

            # if bottom position is attained
            # for bottom point, bottom co-ordinate will be
            # height of window - height of label
            if y < self.w_height - self.l_height:
                self.label.move(x, y + self.speed)

        # if left arrow key is pressed
        elif event.key() == Qt.Key_Left:

            # if left end position is attained
            if x > 0:
                self.label.move(x - self.speed, y)

        # if down arrow key is pressed
        elif event.key() == Qt.Key_Right:

            # if right end position is attained
            # for right end point, right co-ordinate will be
            # width of window - width of label
            if x < self.w_width - self.l_width:
                self.label.move(x + self.speed, y)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-429428-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200611030307/Python-2020-06-11-03-02-37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200611030307/Python-2020-06-11-03-02-37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200611030307/Python-2020-06-11-03-02-37.mp4)</video>