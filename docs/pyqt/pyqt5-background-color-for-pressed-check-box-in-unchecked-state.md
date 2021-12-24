# PyQt5–未选中状态下按下复选框的背景颜色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-背景色-按下-复选框-未选中-状态/](https://www.geeksforgeeks.org/pyqt5-background-color-for-pressed-check-box-in-unchecked-state/)

在本文中，我们将看到如何设置复选框的颜色，当它在未选中状态下被按下时。默认情况下，复选框的标签部分不设置任何按下的颜色，尽管指示器按下时默认为浅蓝色背景。

为了在从未选中状态按下时给复选框添加背景色，我们必须编辑与复选框对象一起使用的样式表代码。下面是样式表代码。

```py
QCheckBox::unchecked:pressed
{
background-color : pink;
}

```

下面是实现。

```py
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

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # adding background color to the pressed check box label part
        # when it is in unchecked state
        checkbox.setStyleSheet("QCheckBox::unchecked:pressed"
                               "{"
                               "background-color : pink;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392129-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330020311/Python-30-03-2020-02_02_50.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330020311/Python-30-03-2020-02_02_50.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330020311/Python-30-03-2020-02_02_50.mp4)</video>