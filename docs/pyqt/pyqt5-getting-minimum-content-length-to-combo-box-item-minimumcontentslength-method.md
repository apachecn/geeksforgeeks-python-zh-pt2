# PyQt5–获取组合框项目的最小内容长度|最小内容长度()方法

> 原文:[https://www . geesforgeks . org/pyqt5-get-最小内容长度到组合框-item-minimum contentslength-method/](https://www.geeksforgeeks.org/pyqt5-getting-minimum-content-length-to-combo-box-item-minimumcontentslength-method/)

在本文中，我们将看到如何获得组合框项目的最小长度，也就是说，这个属性保存了组合框应该容纳的最小字符数。为此，我们将使用 setMinimumContentsLength 方法，默认情况下，组合框的最小长度为 0。
为了得到最小的内容长度，我们将使用 minimumContentsLength 方法。

> **语法:**combo _ box . minimummcontentslength()
> **参数:**不需要参数
> **返回:**返回整数

下面是实现–

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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Saiyan", "Super Sayian 2",
                                              "Super Sayian B"]

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting minimum content length
        self.combo_box.setMinimumContentsLength(3)

        # getting minimum content length
        mini = self.combo_box.minimumContentsLength()

        # creating label to show minimum length
        label = QLabel("Minimum length = " + str(mini), self)

        # setting geometry of the label
        label.setGeometry(150, 100, 350, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/e7571b33d4d75150852c4c6a82e9b6d5.png)