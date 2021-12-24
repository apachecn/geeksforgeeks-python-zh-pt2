# PyQt5 QSpinBox–按下时向向下箭头添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加边框到向下箭头-按下时/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-to-the-down-arrow-when-pressed/)

在本文中，我们将看到如何在向下箭头被按下时为其添加边框，我们知道旋转框中存在两个向上和向下按钮，向下箭头是向下按钮的内部部分。向下箭头是向下按钮的子集，向下按钮是旋转框的子集。默认情况下，向下箭头没有边框。自定义边框仅在按下向下箭头时出现。

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```
QSpinBox::down-arrow:pressed
{
border : 4px solid green;
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
        self.spin.setGeometry(100, 100, 250, 60)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet to the spin box
        # adding border to the down button
        # adding border to the down arrow
        # when it get pressed
        self.spin.setStyleSheet("QSpinBox::down-button"
                                "{"
                                "border : 3px solid pink;"
                                "}"
                                "QSpinBox::down-arrow:pressed"
                                "{"
                                "border : 4px solid green;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411122-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512032612/Python-12-05-2020-03_25_45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512032612/Python-12-05-2020-03_25_45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512032612/Python-12-05-2020-03_25_45.mp4)</video>