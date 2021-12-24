# pyqt 5–检查下拉项目在组合框

中是否隐藏

> 原文:[https://www . geesforgeks . org/pyqt 5-检查-如果-下拉-项目-隐藏或不在-组合框中/](https://www.geeksforgeeks.org/pyqt5-checking-if-drop-down-items-are-hidden-or-not-in-combobox/)

在本文中，我们将看到如何检查下拉框中的组合框项目是否隐藏，即在视图框中是否隐藏。为了做到这一点，我们必须得到组合框的视图对象，并检查它。

> **为了检查项目是否隐藏，我们必须执行以下步骤–**
> 
> 1.创建组合框
> 2。向组合框
> 3 添加项目。获取组合框
> 4 的查看对象。检查查看对象是否隐藏
> 5。创建标签以显示隐藏状态

**语法:**

```py
# getting view part of combo box
view = self.combo_box.view()

# checking if the view object is hidden or not
status = view.isHidden()

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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # getting view part of combo box
        view = self.combo_box.view()

        # making view box hidden
        view.setHidden(True)

        # checking if the view object is hidden or not
        status = view.isHidden()

        # creating label to show the status
        label = QLabel("Hidden ?: " + str(status), self)

        # setting geometry of the label
        label.setGeometry(200, 100, 300, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8ae40392fe1803a620034a7c78066b9d.png)