# PyQt5–停止登记复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-停止登记复选框/](https://www.geeksforgeeks.org/pyqt5-stop-checking-in-checkbox/)

在本文中，我们将看到如何停止复选框以获得选中。有时，在创建表单时，需要停止复选框才能选中。为了做到这一点，我们必须使用`setCheckable`方法，并将其设置为假，这将停止按钮进行检查。

> **语法:**复选框。设置可检查(假)
> 
> **自变量:**它以 bool 为自变量。
> 
> **执行的动作:**它将停止复选框以被选中。

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
        checkbox.setGeometry(200, 150, 100, 40)

        # stooping check box to get checked
        checkbox.setCheckable(False)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-391969-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329013957/Python-29-03-2020-01_38_54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329013957/Python-29-03-2020-01_38_54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329013957/Python-29-03-2020-01_38_54.mp4)</video>