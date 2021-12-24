# PyQt5 QLabel–检查模糊效果是否为窗口类型

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlabel-检查模糊效果是否为窗口类型/](https://www.geeksforgeeks.org/pyqt5-qlabel-checking-if-the-blur-effect-is-window-type/)

在本文中，我们将看到如何检查标签的模糊效果是否是窗口类型。窗口类型允许用户知道模糊效果对象是否像主窗口、弹出窗口等一样是窗口类型。

为了检查模糊效果是否是窗口类型，我们使用`isWindowType`方法。

> **语法:** blur_effect.isWindowType()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

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

        # creating label
        label = QLabel("Label", self)

        # setting geometry to the label
        label.setGeometry(200, 100, 150, 60)

        # setting alignment to the label
        label.setAlignment(Qt.AlignCenter)

        # setting font
        label.setFont(QFont('Arial', 15))

        # setting style sheet of the label
        label.setStyleSheet("QLabel"
                            "{"
                            "border : 2px solid green;"
                            "background : lightgreen;"
                            "}")

        # creating a blur effect
        self.blur_effect = QGraphicsBlurEffect()

        # setting blur radius
        self.blur_effect.setBlurRadius(15)

        # adding blur effect to the label
        label.setGraphicsEffect(self.blur_effect)

        # creating a result label
        result = QLabel(self)

        # setting geometry to the result
        result.setGeometry(200, 200, 300, 30)

        # checking if blur effect is window type
        check = self.blur_effect.isWindowType()

        # setting text to the result
        result.setText("Window type ? : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/fdae520ca5c2a027f4af3c086d6263e3.png)