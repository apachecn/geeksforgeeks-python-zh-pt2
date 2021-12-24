# PyQt5 标签–访问阴影颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-label-access-shadow-color/](https://www.geeksforgeeks.org/pyqt5-label-accessing-shadow-color/)

在本文中，我们将看到我们如何访问标签的阴影颜色，当我们创建标签的阴影时，它默认为黑色，尽管我们可以借助`setColor`方法来改变它的颜色。

> 为了借助`color`方法访问标签的阴影颜色
> 
> **语法:** shadow.color()
> 这里的 shadow 是 QGraphicsDropShadowEffect 对象
> 
> **论证:**不需要论证
> 
> **返回:**返回 QColor 对象

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
        shadow.setBlurRadius(20)

        # setting border color
        shadow.setColor(Qt.green)

        # adding shadow to the label
        label.setGraphicsEffect(shadow)

        # creating label to show the color
        result = QLabel(self)

        # setting geometry
        result.setGeometry(100, 200, 350, 30)

        # getting shadow color
        shadow_color = shadow.color()

        # showing text through label
        result.setText("Shadow color : " + str(shadow_color))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/39d464cd42f4b00bf3b5403571584afa.png)