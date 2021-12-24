# PyQt5 QSpinBox–向向下按钮

添加边框

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-add-border-to-the-down-button/](https://www.geeksforgeeks.org/pyqt5-qspinbox-add-border-to-the-down-button/)

在本文中，我们将看到如何添加边框到旋转框的向下按钮。旋转框由向上和向下两个按钮组成，向下按钮用于减少值，它有自己的默认边框，尽管我们可以更改它。下面是自定义边框的向下按钮的外观。

![](img/32e5787ebf301a623f7e022259162d66.png)；

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```
QSpinBox::down-button
{
border : 4px solid red;
}

```

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet to the spin box
        # adding border to the down button of spin box
        self.spin.setStyleSheet("QSpinBox::down-button"
                                "{"
                                "border : 4px solid red;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e0c760d7b24cadaf9a8ccbdc9e0c44e8.png)