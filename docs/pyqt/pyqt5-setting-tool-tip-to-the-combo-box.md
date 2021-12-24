# PyQt5–将工具提示设置到组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-工具-提示-组合框/](https://www.geeksforgeeks.org/pyqt5-setting-tool-tip-to-the-combo-box/)

在本文中，我们将看到如何设置组合框的工具提示。工具提示基本上是当鼠标悬停在组合框小部件上时出现的提示，为了将工具提示设置到组合框中我们使用`setToolTip`方法。

**注意:**工具提示仅在鼠标悬停在组合框上而不是下拉视图上时可见

> **语法:**组合框.设置工具提示(提示)
> 
> **自变量:**以字符串为自变量
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

        # geek list
        geek_list = ["Sayian", "Super Sayian"]

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # tool tip
        tip = "Sayian Tip"

        # setting tool tip to the combo box
        self.combo_box.setToolTip(tip)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c056a2dc61e425289cd7b1c14cf6b6c9.png)