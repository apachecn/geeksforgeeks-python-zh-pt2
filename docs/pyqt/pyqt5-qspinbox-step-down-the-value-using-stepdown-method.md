# PyQt5 QSpinBox–使用降压方法

降低数值

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-逐步降低价值-使用逐步降低的方法/](https://www.geeksforgeeks.org/pyqt5-qspinbox-step-down-the-value-using-stepdown-method/)

在本文中，我们将看到如何使用`setDown`方法来降低旋转框的值，我们也可以借助箭头按钮来提高旋转框的值，但是为了降低值，我们使用`setDown`方法。

为了做到这一点，我们使用`setDown`方法。

> **语法:**自旋 _box.setDown()
> 
> **论证:**不需要论证
> 
> **执行的动作:**减少旋转框的值

**实施步骤:**
1。创建旋转框
2。创建一个按钮
3。向按钮
4 添加动作。在动作内部调用 stepDown 方法

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

        # step down the value of spin box
        self.spin.stepDown()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410706-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200511004840/Python-11-05-2020-00_48_15.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200511004840/Python-11-05-2020-00_48_15.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200511004840/Python-11-05-2020-00_48_15.mp4)</video>