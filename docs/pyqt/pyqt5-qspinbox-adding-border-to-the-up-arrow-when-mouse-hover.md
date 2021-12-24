# PyQt5 QSpinBox–鼠标悬停时向上箭头添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-鼠标悬停时将边框添加到向上箭头/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-border-to-the-up-arrow-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在向上箭头上时，我们如何给它添加边框，我们知道旋转框中有两个向上和向下的按钮，向上箭头是向上按钮的内部部分。向上箭头是向上按钮的子集，向上按钮是旋转框的子集。默认情况下，向上箭头没有边框，尽管我们可以添加它，但自定义边框只会在鼠标悬停在它上面时出现。

为了做到这一点，我们必须改变与旋转框相关的样式表代码，下面是样式表代码

```
QSpinBox::down-arrow:hover
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
        self.spin.setGeometry(100, 100, 250, 60)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # setting style sheet to the spin box
        # adding border to the down button
        # adding border to the up arrow
        # when mouse hover over it
        self.spin.setStyleSheet("QSpinBox::up-button"
                                "{"
                                "border : 3px solid lightgreen;"
                                "}"
                                "QSpinBox::up-arrow:hover"
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

<video class="wp-video-shortcode" id="video-411111-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512025333/Python-12-05-2020-02_53_15.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512025333/Python-12-05-2020-02_53_15.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512025333/Python-12-05-2020-02_53_15.mp4)</video>