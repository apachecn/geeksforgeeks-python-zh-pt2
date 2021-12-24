# PyQt5 QSpinBox–确保抛光

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-确保-抛光/](https://www.geeksforgeeks.org/pyqt5-qspinbox-ensuring-polished/)

在本文中，我们将了解如何确保旋转盒被抛光。旋转盒的抛光是通过使用 QStyle 或样式表来完成的。抛光是在所有编辑完成的最后完成的，尽管开发者可以通过使用`ensurePolished`方法来确保抛光完成。

> 为了做到这一点，我们使用确保抛光方法
> 
> **语法:**旋转框。确保抛光()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

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

        # setting range to the spin box
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # ensuring spin box is polished
        self.spin.ensurePolished()

        # setting style sheet
        self.spin.setStyleSheet("QSpinBox"
                                "{"
                                "border : 2px solid black;"
                                "background : lightgray;"
                                "}"
                                "QSpinBox::hover"
                                "{"
                                "background : lightblue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-414123-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200518001403/Python-2020-05-18-00-13-35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200518001403/Python-2020-05-18-00-13-35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200518001403/Python-2020-05-18-00-13-35.mp4)</video>