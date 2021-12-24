# PyQt5 QSpinBox–向向下箭头

添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-向下箭头添加边框/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-to-the-down-arrow/)

在本文中，我们将看到如何为向下箭头添加边框，我们知道旋转框中存在两个向上和向下按钮，向下箭头是向下按钮的内部部分。向下箭头是向下按钮的子集，向下按钮是旋转框的子集。默认情况下，向下箭头没有边框，下图显示了向下箭头的边框外观。

![](img/5d3ffb4d23b82c6f32dbd0b32652b3bc.png)

为此，我们必须更改与旋转框相关联的样式表代码，下面是样式表代码

```py
QSpinBox::down-arrow
{
border : 4px solid green;
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
        self.spin.setGeometry(100, 100, 250, 60)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet to the spin box
        # adding border to the down button
        # adding border to the down arrow
        self.spin.setStyleSheet("QSpinBox::down-button"
                                "{"
                                "border : 3px solid pink;"
                                "}"
                                "QSpinBox::down-arrow"
                                "{"
                                "border : 4px solid green;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/522c3f0e589a392c949775f3dbcbe14d.png)