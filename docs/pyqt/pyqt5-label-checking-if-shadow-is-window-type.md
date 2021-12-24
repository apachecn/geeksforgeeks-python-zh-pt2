# PyQt5 标签–检查阴影是否为窗口类型

> 原文:[https://www . geesforgeks . org/pyqt 5-标签检查-如果阴影是窗口类型/](https://www.geeksforgeeks.org/pyqt5-label-checking-if-shadow-is-window-type/)

在本文中，我们将看到如何检查标签阴影是否是窗口类型。窗口类型是指示对象是否是窗口的属性。

> 为了做到这一点，我们使用`isWindowType`方法
> 
> **语法:** shadow.isWindowType()
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

        # creating label
        label = QLabel("Label", self)

        # setting alignment
        label.setAlignment(Qt.AlignCenter)

        # setting geometry to the label
        label.setGeometry(200, 100, 150, 60)

        # setting border
        label.setStyleSheet("border : 8px solid black")

        # creating a QGraphicsDropShadowEffect object
        self.shadow = QGraphicsDropShadowEffect()

        # setting blur radius
        self.shadow.setBlurRadius(30)

        # adding shadow to the label
        label.setGraphicsEffect(self.shadow)

        # checking if shadow is window type
        check = self.shadow.isWindowType()

        # making label
        result = QLabel(self)

        # setting geometry
        result.setGeometry(200, 200, 300, 30)

        # setting text
        result.setText("Window type ? : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8a1e7b5ab164e44bebce814b724bf77e.png)