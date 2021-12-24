# PyQt5 QSpinBox–添加动作

> 原文:[https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-action/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-action/)

在本文中，我们将看到如何向旋转框添加动作，动作基本上是旋转框每次改变值时调用的方法。每次用户更改值时，都会在旋转框中添加操作。

为了增加动作，我们将使用`spin_box.valueChanged.connect`方法。

> **语法:**旋转框.值已更改.连接(方法名)
> 
> **自变量:**以方法名为自变量
> 
> **执行的操作:**每次旋转框的值改变时，都会调用方法

**实施步骤:**

1.创建旋转框
2。创建标签以显示值
3。将动作添加到旋转框
4。在 action 方法内部，获取当前值并通过标签显示它

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
        self.spin.setGeometry(100, 100, 100, 40)

        # adding action to the spin box
        self.spin.valueChanged.connect(self.show_result)

        # creating label show result
        self.label = QLabel(self)

        # setting geometry
        self.label.setGeometry(100, 200, 200, 40)

    # method called by spin box
    def show_result(self):

        # getting current value
        value = self.spin.value()

        # setting value of spin box to the label
        self.label.setText("Value : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-405976-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200430235849/Python-30-04-2020-23_52_45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200430235849/Python-30-04-2020-23_52_45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200430235849/Python-30-04-2020-23_52_45.mp4)</video>