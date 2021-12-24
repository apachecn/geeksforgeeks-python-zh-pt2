# PyQt5 QSpinBox–使用逐步方法更改值

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-使用逐步方法更改值/](https://www.geeksforgeeks.org/pyqt5-qspinbox-changing-value-using-stepby-method/)

在本文中，我们将看到如何使用`setBy`方法更改旋转框的值，我们也可以借助箭头按钮增加旋转框的值，但是为了更改值，我们使用`setBy`方法，该方法将传递的值添加到当前值。

为了做到这一点，我们使用`setBy`方法。

> **语法:**旋转框
> 
> **自变量:**以整数为自变量
> 
> **执行的动作:**改变旋转框的值

**实施步骤:**
1。创建旋转框
2。创建一个按钮
3。向按钮
4 添加动作。在操作中调用逐步方法

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

        # creating a push button
        push = QPushButton("Press", self)

        # setting geometry to the push button
        push.setGeometry(100, 200, 100, 40)

        # adding action to the push button
        push.clicked.connect(self.do_action)

    # method called by push button
    def do_action(self):

        # change value by 5 steps
        self.spin.stepBy(5)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410708-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200511010657/Python-11-05-2020-01_06_22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200511010657/Python-11-05-2020-01_06_22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200511010657/Python-11-05-2020-01_06_22.mp4)</video>