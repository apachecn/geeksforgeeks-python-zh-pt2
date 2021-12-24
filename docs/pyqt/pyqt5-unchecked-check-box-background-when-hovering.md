# PyQt5–悬停时未选中复选框背景

> 原文:[https://www . geesforgeks . org/pyqt 5-未选中-复选框-背景-悬停时/](https://www.geeksforgeeks.org/pyqt5-unchecked-check-box-background-when-hovering/)

在这篇文章中，我们将看到如何设置背景颜色的复选框标签部分时，鼠标悬停，它是在当前选中的状态。

为了做到这一点，我们必须改变复选框的样式表，当鼠标悬停在复选框上时，必须为选中状态添加背景色。下面是样式表代码。

```py
QCheckBox::checked:hover
{
background-color : pink;
}
```

下面是实现。

## 蟒蛇 3

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
        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # adding background color to the check box label part
        # when it is in checked state when mouse hover over it
        checkbox.setStyleSheet("QCheckBox::checked:hover"
                               "{"
                               "background-color : pink;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392135-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330022737/Python-30-03-2020-02_26_44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330022737/Python-30-03-2020-02_26_44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330022737/Python-30-03-2020-02_26_44.mp4)</video>