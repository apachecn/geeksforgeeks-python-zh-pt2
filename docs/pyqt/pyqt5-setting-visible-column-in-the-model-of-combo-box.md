# PyQt5–在组合框

的模型中设置可见列

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-可见-组合框模型中的列/](https://www.geeksforgeeks.org/pyqt5-setting-visible-column-in-the-model-of-combo-box/)

在本文中，我们将看到如何设置组合框的可见列。这用于设置用户可见的列，model column 属性保存模型中可见的列。为了设置这个，我们使用`setModelColumn`方法。

> **语法:**组合框. setModelColumn(n)
> 
> **自变量:**以整数为自变量，即列索引
> 
> **返回:**无

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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # setting visible model column 
        self.combo_box.setModelColumn(0)

        # geek list
        geek_list = ["Sayian", "Super Saiyan", "Super Sayian 2", "Super Sayian B"]

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/ac8024a0a3f435b5d7d7b7221b9116ab.png)