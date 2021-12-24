# PyQt5 QSpinBox–向上按钮添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-向上按钮添加边框/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-to-the-up-button/)

在本文中，我们将看到如何添加边框到旋转框的向上按钮。旋转框由向上和向下两个按钮组成，向上按钮用于增加值，它有自己的默认边框，尽管我们可以更改它。下面是自定义边框的向上按钮的外观。

![](img/1ad84cb0970515feeed13709d6fe4d8f.png)

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```py
QSpinBox::up-button
{
border : 4px solid blue;
}

```

下面是实现

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet to the spin box
        # adding border to the up button of spin box
        self.spin.setStyleSheet("QSpinBox::up-button"
                                "{"
                                "border : 4px solid blue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/29dd5302a23a6956ddca10090053e087.png)