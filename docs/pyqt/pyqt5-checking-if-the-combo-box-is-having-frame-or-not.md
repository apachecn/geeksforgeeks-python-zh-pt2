# PyQt5–检查组合框是否有框架

> 原文:[https://www . geesforgeks . org/pyqt 5-检查组合框是否有框架/](https://www.geeksforgeeks.org/pyqt5-checking-if-the-combo-box-is-having-frame-or-not/)

在本文中，我们将看到如何找到组合框是否有框架。默认情况下，当我们创建一个组合框，它有框架，虽然我们可以改变它。为了检查帧是否存在，我们使用`hasFrame`方法。

> **语法:**组合框. hasFrame()
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

以下是实施–

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
        self.combo_box.setGeometry(200, 150, 120, 30)

        # geek list
        geek_list = ["Geek", "Geeky Geek", "Legend Geek", "Ultra Legend Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # finding if combo box is having frame or not
        check = self.combo_box.hasFrame()

        # creating label to show check
        label = QLabel("Frame = " + str(check), self)

        # setting geometry of label
        label.setGeometry(200, 200, 200, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/15f3364087b4e53c249c9ea87597c252.png)