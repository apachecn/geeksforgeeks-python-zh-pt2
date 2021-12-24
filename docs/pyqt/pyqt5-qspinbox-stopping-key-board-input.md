# PyQt5 QSpinBox–停止键盘输入

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-stop-key-board-input/](https://www.geeksforgeeks.org/pyqt5-qspinbox-stopping-key-board-input/)

在本文中，我们将看到如何制作一个不能从键盘输入的旋转框，当我们创建一个旋转框时，基本上有两种方法来改变旋转框的值，一种是使用箭头按钮，另一种是使用键盘。停止旋转框的键盘输入意味着用户将无法使用键盘在旋转框中输入值，尽管用户可以使用箭头按钮进行递增或递减。

> 为了停止键盘输入，我们对行编辑对象使用了 setReadOnly 方法
> 
> **语法:** line_edit.setReadOnly(真)
> 
> **自变量:**它以布尔为自变量
> 
> **执行的操作:**将使行编辑对象为只读

**为了做到这一点我们必须做到以下几点:**
1。创建主窗口
2。创建一个旋转框
3。从旋转框
4 中获取线条编辑对象。将线编辑部分设为只读

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

        # getting the line edit
        line = self.spin.lineEdit()

        # making the the line edit part read only
        line.setReadOnly(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411884-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512203619/Python-12-05-2020-20_35_55.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512203619/Python-12-05-2020-20_35_55.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512203619/Python-12-05-2020-20_35_55.mp4)</video>