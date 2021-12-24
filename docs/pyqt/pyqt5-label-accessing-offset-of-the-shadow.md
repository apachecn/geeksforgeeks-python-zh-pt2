# PyQt5 标签–访问阴影偏移

> 原文:[https://www . geesforgeks . org/pyqt 5-标签访问-阴影偏移量/](https://www.geeksforgeeks.org/pyqt5-label-accessing-offset-of-the-shadow/)

在本文中我们将看到如何访问标签阴影的偏移，偏移基本上是标签阴影和标签之间的距离默认偏移值为 8，尽管我们可以借助`setOffset`方法随时更改它。

> 为了做到这一点，我们使用`offset`方法
> 
> **语法:** shadow.offset()
> 这里的 shadow 是 QGraphicsDropShadowEffect 对象
> 
> **论证:**不需要论证
> 
> **返回:**它返回 QPointF 对象作为参数

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

        # setting offset
        shadow.setOffset(100)

        # adding shadow to the label
        label.setGraphicsEffect(shadow)

        # creating label 
        result = QLabel(self)

        # setting geometry
        result.setGeometry(100, 200, 350, 30)

        # getting shadow offset
        offset = shadow.offset()

        # showing text through label
        result.setText("Offset : " + str(offset))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c732769746b622df35508d6269cc8b54.png)