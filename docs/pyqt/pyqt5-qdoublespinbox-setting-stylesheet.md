# PyQt5 QDoubleSpinBox–设置样式表

> 原文:[https://www . geesforgeks . org/pyqt 5-qdoublespinbox-setting-样式表/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-setting-stylesheet/)

在本文中，我们将看到如何将样式表设置为 QDoubleSpinBox。样式表用来设置颜色、背景和双旋转框的各种样式。有了样式表，我们可以给它添加边框，并制作我们自己定制的双旋转框。

> 为了做到这一点，我们将使用双旋转框对象的`setStyleSheet`方法。
> 
> **语法:**DD _ spin . set 样式表(代码)
> 
> **参数:**它以字符串作为参数
> 
> **返回:**返回无

下面是示例样式表代码

```py
QDoubleSpinBox
{
border : 2px solid black;
background : white;
}
QDoubleSpinBox::hover
{
border : 2px solid green;
background : lightgreen;
}
QDoubleSpinBox::up-arrow
{
border : 1px solid black;
background : blue;
}
QDoubleSpinBox::down-arrow
{
border : 1px solid black;
background : red;
}

```

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating double spin box
        d_spin = QDoubleSpinBox(self)

        # setting geometry to the double spin box
        d_spin.setGeometry(100, 100, 150, 40)

        # setting decimal precision
        d_spin.setDecimals(1)

        # step type
        step_type = QAbstractSpinBox.AdaptiveDecimalStepType

        # adaptive step type
        d_spin.setStepType(step_type)

        # setting style sheet to the double spin box
        d_spin.setStyleSheet("QDoubleSpinBox"
                             "{"
                             "border : 2px solid black;"
                             "background : white;"
                             "}"
                             "QDoubleSpinBox::hover"
                             "{"
                             "border : 2px solid green;"
                             "background : lightgreen;"
                             "}"
                             "QDoubleSpinBox::up-arrow"
                             "{"
                             "border : 1px solid black;"
                             "background : blue;"
                             "}"
                             "QDoubleSpinBox::down-arrow"
                             "{"
                             "border : 1px solid black;"
                             "background : red;"
                             "}"
                             )

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-457833-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200723005301/Python-2020-07-23-00-52-45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200723005301/Python-2020-07-23-00-52-45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200723005301/Python-2020-07-23-00-52-45.mp4)</video>