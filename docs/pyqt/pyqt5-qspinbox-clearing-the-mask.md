# PyQt5 QSpinBox–清除屏蔽

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-clearing-the-mask/](https://www.geeksforgeeks.org/pyqt5-qspinbox-clearing-the-mask/)

在本文中，我们将看到如何从旋转框中清除蒙版，蒙版用于隐藏用户界面图像元素的一部分。我们可以使用`setMask`方法设置蒙版。

为了做到这一点，我们使用 cleanText 方法。

> **语法:** spin_box.clearMask()
> 
> **论证:**不需要论证
> 
> **执行的动作:**它屏蔽旋转框

**实施步骤:**
1。创建主窗口
2。创建一个旋转框设置其范围前缀和后缀
3。将蒙版添加到旋转框
4。创建按钮
5。向按钮
6 添加动作。在动作方法内部调用 clearMask 方法

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

        # setting range to the spin box
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a push button
        push = QPushButton("Clear", self)

        # setting geometry to the push button
        push.setGeometry(100, 200, 100, 40)

        # adding action to the push button
        push.clicked.connect(self.push_action)

        # setting mask on spin box
        region = self.spin.childrenRegion()
        self.spin.setMask(region)

    # method called by the push button
    def push_action(self):

        # clearing the mask
        self.spin.clearMask()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-413088-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515022321/Python-15-05-2020-02_22_59.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515022321/Python-15-05-2020-02_22_59.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515022321/Python-15-05-2020-02_22_59.mp4)</video>