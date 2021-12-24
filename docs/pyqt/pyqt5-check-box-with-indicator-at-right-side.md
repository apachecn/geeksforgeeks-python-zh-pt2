# pyqt 5–右侧带指示器的复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-右侧带指示器的复选框/](https://www.geeksforgeeks.org/pyqt5-check-box-with-indicator-at-right-side/)

在本文中，我们将看到如何设置复选框右侧的指示器。复选框基本上有两个组成部分第一个是指示器，另一个是标签默认情况下指示器位于左侧。为了使指示器位于右侧，我们必须将其布局方向从左侧更改为右侧。

为了做到这一点，我们将使用`setLayoutDirection`方法。

> **语法:**checkbox . setlayoutdirection(Qt。RightToLeft)
> 
> **自变量:**它以 Qt 对象为自变量。
> 
> **执行的动作:**将改变复选框的布局。

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

        # changing position of indicator
        checkbox.setLayoutDirection(Qt.RightToLeft)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/922e6879e1384d3b442505c1ed0158d1.png)