# PyQt5 QSpinBox–根据用户删除

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-按用户删除它/](https://www.geeksforgeeks.org/pyqt5-qspinbox-deleting-it-according-to-user/)

在本文中，我们将看到如何在用户命令时删除旋转框，而在设计应用程序时，如果关闭小部件时不小心，它可能会消耗大量空间/内存。基于 QObject 的类被设计成(可选地)在层次结构中链接在一起。当顶级对象被删除时，Qt 也会自动删除它的所有子对象。

为了明确删除旋转框的引用，我们使用`deletLater`方法。

> **语法:**自旋 _ box.deleteLater()
> 
> **论证:**不需要论证
> 
> **执行的动作:**从内存中删除/移除旋转框的引用。

 **实施步骤:**
1。创建一个旋转框
2。创建一个标签来显示旋转盒状态
3。创建按钮
4。向按钮
5 添加动作。在操作中，删除旋转框的引用并更新标签的文本

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
        self.spin.setGeometry(100, 100, 150, 40)

        # setting suffix to spin
        self.spin.setSuffix(" Spin Box")

        # creating label
        self.label = QLabel(self)

        # setting geometry
        self.label.setGeometry(100, 200, 300, 40)

        # setting text to the label
        self.label.setText("Spin box will delete when button get pressed")

        # creating a push button
        push = QPushButton("Press", self)

        # adding action to the push button
        push.pressed.connect(self.push_method)

    # method called by push button
    def push_method(self):

        # deleting the spin box
        self.spin.deleteLater()

        # showing this new name to label
        self.label.setText("Spin box is deleted")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-409776-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200509011618/Python-09-05-2020-01_16_02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200509011618/Python-09-05-2020-01_16_02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200509011618/Python-09-05-2020-01_16_02.mp4)</video>