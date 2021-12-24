# PyQt5 QSpinBox–清除文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-cleaning-the-text/](https://www.geeksforgeeks.org/pyqt5-qspinbox-cleaning-the-text/)

在本文中，我们将看到如何清理旋转框的文本，清理文本意味着删除任何数字之前的空格和零，因为我们知道 001 类似于 1，因此清理文本将删除文本中不需要的零。

为了做到这一点，我们使用 cleanText 方法。

> **语法:**旋转 _box.cleanText()
> 
> **论证:**不需要论证
> 
> **执行的动作:**清除旋转框的文字

**注意:**不包括前缀、后缀或前导或尾随空格。

> 实施步骤:
> 1。创建主窗口
> 2。创建一个旋转框设置其范围前缀和后缀
> 3。创建按钮
> 4。给按钮增加动作
> 5。在操作方法内部，调用 cleanText 方法

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

        # setting range to the spin box
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a push button
        push = QPushButton("Clean", self)

        # setting geometry to the push button
        push.setGeometry(100, 200, 100, 40)

        # adding action to the push button
        push.clicked.connect(self.push_action)

    # method called by the push button
    def push_action(self):

        # cleaning the text
        self.spin.cleanText()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-413086-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515020021/Python-15-05-2020-01_59_45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515020021/Python-15-05-2020-01_59_45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515020021/Python-15-05-2020-01_59_45.mp4)</video>