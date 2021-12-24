# PyQt5–在进度条

上添加边框

> 原文:[https://www . geesforgeks . org/pyqt 5-进度条添加边框/](https://www.geeksforgeeks.org/pyqt5-adding-border-to-bar-of-progress-bar/)

在本文中，我们将看到如何添加边框到进度条。进度条基本上有两个部分，一个是背景，另一个是根据百分比改变大小的条。下面是普通进度条与进度条边框的图示。

![](img/42eeafeade6de347c0fa6cc739b711f7.png) ![](img/564efcd48826b42087d98ae74d5aabbc.png)

为了给条形图添加边框，我们必须改变 CSS 样式表，并使用`setStyleSheet`方法，下面是样式表代码

```
QProgressBar
{
border : 1px solid black;
}
QProgressBar
{
border : 3px solid red;
}

```

下面是实现。

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

        # setting background color to window
        # self.setStyleSheet("background-color : yellow")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # creating progress bar
        bar = QProgressBar(self)

        # setting geometry to progress bar
        bar.setGeometry(200, 100, 200, 30)

        # setting the value
        value = 70
        bar.setValue(value)

        # setting alignment to center
        bar.setAlignment(Qt.AlignCenter)

        # setting border to progress bar 
        # and setting border to the bar and color
        bar.setStyleSheet("QProgressBar "
                          "{"
                          "border : 1px solid black;"
                          "}"
                          "QProgressBar::chunk"
                          "{"
                          "background-color : yellow;"
                          "border :3px solid red;"
                          "}"
                          )

App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f3bb2cbc133f08cb9ff20a4fcccde008.png)