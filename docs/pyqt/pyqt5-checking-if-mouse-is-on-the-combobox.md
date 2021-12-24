# PyQt5–检查鼠标是否在组合框上

> 原文:[https://www . geesforgeks . org/pyqt 5-检查鼠标是否在组合框上/](https://www.geeksforgeeks.org/pyqt5-checking-if-mouse-is-on-the-combobox/)

在本文中，我们将看到如何知道鼠标/光标是否在组合框上，为了做到这一点，我们使用`underMouse`方法，每次调用该函数时，它都会检查鼠标的位置，并检查其位置是否在组合框上。

为了做到这一点，我们使用`underMouse`方法。

> **语法:**组合框.鼠标下()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

**实施步骤:**

1.创建组合框
2。创建一个标签来显示结果
3。创建一个每 100 毫秒调用一个函数的定时器对象
4。在定时器功能中，检查组合框是否在鼠标
5 下。通过标签显示结果

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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 100, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting stylesheet of the combo box
        self.combo_box.setStyleSheet("border : 1px solid red;")

        # creating label to show label
        self.label = QLabel(self)

        # setting geometry to the label
        self.label.setGeometry(200, 200, 200, 30)

        # creating a timer object
        timer = QTimer(self)

        # adding action to the timer
        timer.timeout.connect(self.do_something)

        # starting timer
        timer.start(100)

    # action called by the timer
    def do_something(self):

        # checking if the combo box is under mouse
        under = self.combo_box.underMouse()

        # setting text to the label
        self.label.setText("Under Mouse ? : " + str(under))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407959-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200506001655/Python-06-05-2020-00_12_16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200506001655/Python-06-05-2020-00_12_16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200506001655/Python-06-05-2020-00_12_16.mp4)</video>