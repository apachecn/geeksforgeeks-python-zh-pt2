# PyQt5 QComboBox–检查鼠标跟踪是否激活

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcombobox-checking-如果鼠标跟踪被激活或未被激活/](https://www.geeksforgeeks.org/pyqt5-qcombobox-checking-if-mouse-tracking-is-activated-or-not/)

在本文中，我们将看到如何检查组合框的鼠标跟踪是否被激活，当任何按钮被按下时，组合框接收关于鼠标的信号，但是在鼠标跟踪之后，即使没有按下任何按钮，它也将接收关于鼠标的所有信号。默认情况下，该属性为假，尽管我们可以借助`setMouseTracking`方法激活鼠标跟踪。

为了做到这一点，我们使用`hasMouseTracking`方法

> **语法:**组合框. hasMouseTracking()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 100, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting mouse tracking
        self.combo_box.setMouseTracking(True)

        # setting stylesheet of the combo box
        self.combo_box.setStyleSheet("border : 1px solid red;")

        # creating label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(200, 200, 200, 40)

        # getting mouse tracking
        tracking = self.combo_box.hasMouseTracking()

        # setting text to the label
        label.setText("Mouse tracking enabled ? : " + str(tracking))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/ba4a6be996e3bfb69206855a08072c65.png)