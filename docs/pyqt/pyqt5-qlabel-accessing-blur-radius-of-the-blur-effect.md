# PyQt5 QLabel–访问模糊效果的模糊半径

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qlabel-访问-模糊-模糊半径-效果/](https://www.geeksforgeeks.org/pyqt5-qlabel-accessing-blur-radius-of-the-blur-effect/)

在本文中，我们将看到如何访问标签模糊效果的模糊半径。模糊半径(必需的)，如果设置为 0，阴影将是清晰的，数字越高，它将越模糊。默认情况下，模糊半径值为 5.0，我们可以随时更改它。

为了做到这一点，我们使用`blurRadius`方法。

> **语法:** blur_effect.blurRadius()
> 这里的 blur_effect 是 QGraphicsBlurEffect 对象
> 
> **论证:**不需要论证
> 
> **返回:**返回 foat 值

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

        # getting blur radius
        b_radius = self.blur_effect.blurRadius()

        # setting text to the result
        result.setText("Blur radius = " + str(b_radius))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/318a2f9b93842dc5510f789837a90a26.png)