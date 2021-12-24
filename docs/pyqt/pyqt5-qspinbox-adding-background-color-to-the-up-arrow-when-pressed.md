# PyQt5 QSpinBox–按下时向上箭头添加背景色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-背景色-向上箭头-按下时/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-color-to-the-up-arrow-when-pressed/)

在这篇文章中，我们将看到如何设置背景颜色旋转框的向上箭头时，它被按下。旋转框基本上有三个组成部分一个是行编辑另外两个是上下按钮。向上箭头是向上按钮的内部部分，只有当向上箭头被按下时，这个背景颜色才会出现。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox::up-arrow:pressed
{
background-color : blue;
}

```

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

        # setting style sheet of spin box
        # adding background color to the up-arrow when it get pressed
        self.spin.setStyleSheet("QSpinBox::up-arrow::pressed"
                                "{"
                                "background-color : blue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411931-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513023708/Python-13-05-2020-02_36_31.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513023708/Python-13-05-2020-02_36_31.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513023708/Python-13-05-2020-02_36_31.mp4)</video>