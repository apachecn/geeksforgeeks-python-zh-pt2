# PyQt5 组合框–不同边框尺寸厚度

> 原文:[https://www . geesforgeks . org/pyqt 5-组合框-不同边框-尺寸-厚度/](https://www.geeksforgeeks.org/pyqt5-combo-box-different-border-size-thickness/)

在本文中，我们将看到如何创建一个组合框，它有不同的边框尺寸，即不同边的厚度。下面是组合框在不同边框尺寸下的外观

![](img/89c93a8b21d638499766cc3c8548c330.png)

为此，我们必须更改与组合框关联的样式表代码，下面是样式表代码

```py
QComboBox
{
border : solid black;
border-width : 5px 5px 1px 1px;
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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet to the combo box
        # setting background with different thickness 
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : solid black;"
                                     "border-width : 6px 5px 1px 1px;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/6671c9aee35cd917350a328a21bad2a9.png)