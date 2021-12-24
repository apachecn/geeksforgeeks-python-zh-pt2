# PyQt5–复选框

中指示器的凹槽边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-凹槽-边框到指示器-在复选框中/](https://www.geeksforgeeks.org/pyqt5-groove-border-to-indicator-in-check-box/)

在本文中，我们将看到如何设置凹槽边框的指标复选框。默认情况下，复选框的指示器有边框，虽然我们可以更改边框的大小，但它将是普通的边框。下面是复选框指示器的凹槽边框表示。
![](img/eb6ab6905c104e252d01e11fc4084e81.png)

为了给复选框的指示器添加凹槽边框，我们必须编辑与复选框对象一起使用的样式表，下面是指示器凹槽边框的样式表代码。

```
QCheckBox::indicator
{
border : 5px blue;
border-style : groove;
}

```

下面是实现。

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

        # creating the check-box
        checkbox = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # adding groove border to the indicator
        checkbox.setStyleSheet("QCheckBox::indicator"
                               "{"
                               "border : 5px solid blue;"
                               "border-style : groove;"
                               "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b6bcfb2a9109270f490d68cd09ca5ef4.png)