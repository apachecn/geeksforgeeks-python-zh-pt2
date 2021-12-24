# PyQt5–带虚线边框的进度条

> 原文:[https://www . geeksforgeeks . org/pyqt 5-带虚线边框的进度条/](https://www.geeksforgeeks.org/pyqt5-progress-bar-with-dotted-border/)

在本文中，我们将看到如何创建进度条的虚线边框。默认情况下，进度条的边框是连续的。下面是普通边框进度条和虚线边框进度条的图示。

![](img/5fdcbc46b9fc9297ef524441a571ba2e.png) ![](img/0fbd9e513c559aa705db29baa3cbd9ac.png)

为了做到这一点，我们必须改变 CSS 样式表，下面是可以和`setStyleSheet`方法一起使用的样式表代码。

```py
QProgressBar
{
border : 3px black;
border-style : dotted;
}

```

下面是实现。

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

        # setting background color to window
        # self.setStyleSheet("background-color : yellow")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # creating progress bar
        bar = QProgressBar(self)

        # setting geometry to progress bar
        bar.setGeometry(200, 100, 200, 30)

        # setting the value
        value = 70
        bar.setValue(value)

        # setting alignment to center
        bar.setAlignment(Qt.AlignCenter)

        # setting dotted border
        bar.setStyleSheet("QProgressBar "
                          "{"
                          "border : 3px black;"
                          "border-style :dotted"
                          "}"
                          )

App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9be94ad22dcf9980d451b0c7c1a5c5a7.png)