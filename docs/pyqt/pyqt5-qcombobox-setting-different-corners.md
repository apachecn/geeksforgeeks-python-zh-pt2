# PyQt5 QComboBox–设置不同的角

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcombobox-setting-differential-corners/](https://www.geeksforgeeks.org/pyqt5-qcombobox-setting-different-corners/)

在本文中，我们将看到如何为组合框设置不同的角，组合框小部件不同于其他小部件，它由许多其他小部件组成，例如，文本视图、按钮、行编辑等。

为了使组合框循环，我们必须更改与组合框关联的样式表，下面是样式表代码

```
QComboBox
{
border : 1px solid black;
border-top-left-radius : 20px;
border-top-right-radius : 2px;
border-bottom-left-radius:5px;
border-bottom-right-radius : 3px;
}

```

**注意:**它只使组合框主小部件即文本视图部分循环，对按钮没有影响。

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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 100, 40)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting stylesheet of the combo box
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : 1px solid black;"
                                     "border-top-left-radius : 20px;"
                                     "border-top-right-radius : 2px;"
                                     "border-bottom-left-radius:5px;"
                                     "border-bottom-right-radius : 3px;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/2b00d343480fdb3020cd4ef685bd3848.png)