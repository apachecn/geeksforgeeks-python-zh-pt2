# PyQt5 QSpinBox–为反按状态的向下按钮添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-为反按状态添加边框按钮/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-to-the-down-button-for-anti-pressed-state/)

在这篇文章中，我们将看到如何添加边框到旋转框的向下按钮，当它是反按状态。旋转框由向上和向下两个按钮组成，向下按钮用于减少值，它有自己的默认边框，尽管我们可以更改它。只有当按钮未按下时，自定义边框才会出现在向下按钮上，否则会出现正常边框。

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```
QSpinBox::down-button:!pressed
{
border : 4px solid red;
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

        # setting style sheet to the spin box
        # adding border to the down button of spin box
        # and it is in anti pressed state
        self.spin.setStyleSheet("QSpinBox::down-button:! pressed"
                                "{"
                                "border : 4px solid red;"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411108-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512023438/Python-12-05-2020-02_34_20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512023438/Python-12-05-2020-02_34_20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512023438/Python-12-05-2020-02_34_20.mp4)</video>