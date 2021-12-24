# PyQt5 QSpinBox–当鼠标悬停在向上按钮上时，为其添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-鼠标悬停在按钮上时添加边框/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-to-the-up-button-when-mouse-hover-over-it/)

在这篇文章中，我们将看到如何在鼠标悬停在旋转框的上按钮上时为其添加边框。旋转框由向上和向下两个按钮组成，向上按钮用于增加值，它有自己的默认边框，尽管我们可以更改它。当鼠标悬停在向上按钮上时，自定义边框将出现在向上按钮上。

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```py
QSpinBox::up-button:hover
{
border : 4px solid blue;
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

        # setting style sheet to the spin box
        # adding border to the up button of spin box
        # when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::up-button:hover"
                                "{"
                                "border : 4px solid blue;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410962-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512015411/Python-12-05-2020-01_53_37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512015411/Python-12-05-2020-01_53_37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512015411/Python-12-05-2020-01_53_37.mp4)</video>