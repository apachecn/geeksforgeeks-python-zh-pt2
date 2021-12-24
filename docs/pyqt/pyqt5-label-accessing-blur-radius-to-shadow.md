# PyQt5 标签–访问模糊半径进行阴影

> 原文:[https://www . geesforgeks . org/pyqt 5-标签-访问-模糊-半径到阴影/](https://www.geeksforgeeks.org/pyqt5-label-accessing-blur-radius-to-shadow/)

在本文中，我们将看到如何访问标签阴影的模糊半径。模糊半径，如果设置为 0 阴影会很锐利，数值越高越模糊，默认模糊半径为 0，我们用`setBlurRadius`方法设置模糊半径

> 为了获得标签阴影的模糊半径，我们使用`blurRadius`方法
> 
> **语法:** shadow.blurRadius(n)
> 这里的 shadow 是 QGraphicsDropShadowEffect 对象
> 
> **论证:**不需要论证
> 
> **返回:**返回浮点值

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

        # setting background color of window
        # self.setStyleSheet("background-color : black;")

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
        shadow = QGraphicsDropShadowEffect()

        # setting blur radius
        shadow.setBlurRadius(15)

        # adding shadow to the label
        label.setGraphicsEffect(shadow)

        # creating label to show the blur radius
        result = QLabel(self)

        # setting geometry
        result.setGeometry(200, 200, 200, 30)

        # getting blur radius
        b_radius = shadow.blurRadius()

        # showing text through label
        result.setText("Blur Radius : " + str(b_radius))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/f4af28eb6552c0835ac1f628c8a39e5a.png)