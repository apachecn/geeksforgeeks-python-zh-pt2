# PyQt5 QSpinBox–使旋转框可见

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-making-spin-box-visible/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-spin-box-visible/)

在本文中，我们将看到如何借助`setVisible`方法使旋转框可见。我们可以使用`hide`方法或`setHidden`方法隐藏旋转框。默认情况下，旋转框可见。

为了做到这一点，我们使用`setVisible`方法。

> **语法:** spin_box.setVisible(bool)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

**实施步骤:**
1。创建旋转框
2。创建一个按钮
3。向按钮
4 添加动作。在按钮内部，借助设置隐藏方法
5 隐藏旋转盒。创建另一个按钮
6。在动作内部，借助 setVisible 方法使旋转框可见

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

        # creating push button
        button = QPushButton("Hidden", self)

        # setting button geometry
        button.setGeometry(100, 160, 100, 40)

        # adding action to the push button
        button.clicked.connect(self.push_method)

        # creating push button
        e_button = QPushButton("Visible", self)

        # setting button geometry
        e_button.setGeometry(220, 160, 100, 40)

        # adding action to the push button
        e_button.clicked.connect(self.another_method)

    # method called by push button
    def push_method(self):

        # making spin box hidden
        self.spin.setHidden(True)

    # method called by e_button
    def another_method(self):

        # making spin box visible
        self.spin.setVisible(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410680-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200510020023/Python-10-05-2020-01_59_30.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200510020023/Python-10-05-2020-01_59_30.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200510020023/Python-10-05-2020-01_59_30.mp4)</video>