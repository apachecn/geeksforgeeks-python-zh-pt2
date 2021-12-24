# PyQt5 QSpinBox–对象名称改变时的添加动作

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-添加-操作-当-对象-名称-更改/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-action-when-object-name-changed/)

在本文中我们将看到如何做一些事情旋转框的对象名称被改变，对象名称基本上是赋予旋转框的对象的名称，当我们在 PyQt5 应用程序中借助对象名称借助`findChild`方法找到对象时。借助`setObjectName`方法，可以将对象名称设置到旋转框中。

> 实施步骤–
> 
> 1.创建旋转框
> 2。设置其对象名称
> 3。借助标签
> 4 显示对象名称。当对象名称改变时，给旋转框添加动作，使旋转框的后缀改变
> 5。创建一个按钮
> 6。向按钮添加操作更改旋转框的对象名称

为了在对象名称改变时增加动作，我们使用`objectNameChanged.connect`方法..

> **语法:**spin _ box . object name changed . connect(方法名)
> 
> **自变量:**以方法名为自变量
> 
> **执行的操作:**它将调用传递的方法

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
        self.spin.setGeometry(100, 100, 150, 40)

        # setting suffix to spin
        self.spin.setSuffix(" Spin Box")

        # name
        name = "Geeky"

        # setting up object name
        self.spin.setObjectName(name)

        # adding action when the spin box object name is changed
        self.spin.objectNameChanged.connect(self.spin_method)

        # creating label
        self.label = QLabel(self)

        # setting geometry
        self.label.setGeometry(100, 200, 300, 40)

        # getting object name
        get_name = self.spin.objectName()

        # setting text to the label
        self.label.setText("Object Name : " + get_name)

        # creating a push button
        push = QPushButton("Press", self)

        # adding action to the push button
        push.pressed.connect(self.push_method)

    # method called when object name is changed
    def spin_method(self):
        # setting suffix
        self.spin.setSuffix(" Name changed")

    # method called by push button
    def push_method(self):
        # setting object name of spin box
        self.spin.setObjectName("New")

        # getting object name
        get_name = self.spin.objectName()

        # showing this new name to label
        self.label.setText("Object Name : " + get_name)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-409762-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200509010518/Python-09-05-2020-01_05_05.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200509010518/Python-09-05-2020-01_05_05.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200509010518/Python-09-05-2020-01_05_05.mp4)</video>