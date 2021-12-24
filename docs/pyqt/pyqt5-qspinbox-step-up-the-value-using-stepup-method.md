# PyQt5 QSpinBox–使用逐步增加方法增加数值

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-逐步提升价值-使用逐步提升方法/](https://www.geeksforgeeks.org/pyqt5-qspinbox-step-up-the-value-using-stepup-method/)

在本文中，我们将看到如何使用`setUp`方法增加旋转框的值，我们也可以借助箭头按钮增加旋转框的值，但是为了增加值，我们使用`setUp`方法。

为了做到这一点，我们使用`setUp`方法。

> **语法:**旋转框。设置()
> 
> **论证:**不需要论证
> 
> **执行的动作:**增加旋转框的值

**实施步骤:**
1。创建旋转框
2。创建一个按钮
3。向按钮
4 添加动作。在动作内部调用 stepUp 方法

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

        # step up the value of spin box
        self.spin.stepUp()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410704-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200511002947/Python-11-05-2020-00_28_46.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200511002947/Python-11-05-2020-00_28_46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200511002947/Python-11-05-2020-00_28_46.mp4)</video>