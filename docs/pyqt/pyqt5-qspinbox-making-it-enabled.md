# PyQt5 QSpinBox–启用

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-making-it-enabled/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-it-enabled/)

在这篇文章中，我们将看到如何根据用户启用旋转框，禁用的旋转框基本上是不能编辑的旋转框，即禁用和启用的旋转框是正常的旋转框，默认情况下旋转框是启用的。为了使旋转框失效，我们使用`setDisabled`方法。

为了做到这一点，我们使用`setEnabled`方法。

> **语法:**spin _ box . setenv enabled(bool)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

**实施步骤:**
1。创建旋转框
2。创建一个按钮并在按钮上添加动作
3。在动作内部，使旋转箱禁用
4。创建另一个按钮并添加动作
5。在操作中，启用旋转框

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

        # setting range to spin
        self.spin.setRange(0, 99999)

        # creating push button
        button = QPushButton("Disable", self)

        # setting button geometry
        button.setGeometry(100, 160, 100, 40)

        # adding action to the push button
        button.clicked.connect(self.push_method)

        # creating push button
        e_button = QPushButton("Enable", self)

        # setting button geometry
        e_button.setGeometry(220, 160, 100, 40)

        # adding action to the push button
        e_button.clicked.connect(self.another_method)

    # method called by push button
    def push_method(self):

        # making spin box disabled
        self.spin.setDisabled(True)

    # method called by e_button
    def another_method(self):

        # making spin box enabled
        self.spin.setEnabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410674-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200510004257/Python-10-05-2020-00_42_33.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200510004257/Python-10-05-2020-00_42_33.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200510004257/Python-10-05-2020-00_42_33.mp4)</video>