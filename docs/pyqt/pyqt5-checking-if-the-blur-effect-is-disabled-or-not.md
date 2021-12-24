# pyqt 5–检查模糊效果是否被禁用

> 原文:[https://www . geesforgeks . org/pyqt 5-检查模糊效果是否被禁用/](https://www.geeksforgeeks.org/pyqt5-checking-if-the-blur-effect-is-disabled-or-not/)

在本文中，我们将看到如何检查标签的模糊效果是否被禁用，默认情况下，标签没有模糊效果，尽管我们可以随时添加模糊效果。为了启用或禁用模糊效果，我们使用`setEnable`方法。

为了检查模糊效果是否被禁用和启用，我们使用`isEnable`方法。

> **语法:** blur_effect.isEnabled()
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

        # checking if blur effect is enabled or not
        check = self.blur_effect.isEnabled()

        # setting text to the result
        result.setText("Blur enabled ? : " + str(check))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/288302075e3a89e72ee750e1d151d4c6.png)