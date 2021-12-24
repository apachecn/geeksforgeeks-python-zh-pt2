# PyQt5–在组合框

中获取所选项的角色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-获取组合框中所选项目的角色/](https://www.geeksforgeeks.org/pyqt5-getting-the-role-of-selected-item-in-combobox/)

在本文中，我们将看到如何在组合框中获得所选项的角色。角色基本上是与物品一起提供的附加数据，为了得到所选物品的角色我们使用`currentData`方法。

> **语法:**组合框 _ currentdata()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串，即所选项目的角色

以下是实施–

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
        self.combo_box.setGeometry(200, 150, 120, 30)

        # geek list
        geek_list = ["Geek", "Geeky Geek", "Legend Geek", "Ultra Legend Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting roles to the items
        self.combo_box.setItemData(0, "First role")
        self.combo_box.setItemData(1, "Second role")
        self.combo_box.setItemData(2, "Third role")
        self.combo_box.setItemData(3, "Forth role")

        # create push button
        button = QPushButton("Show", self)

        # adding action to the button
        button.pressed.connect(self.show_role)

        # creating label
        self.label = QLabel(self)

        # setting geometry of the label
        self.label.setGeometry(200, 200, 200, 30)

    def show_role(self):

        # getting the role of selected item
        role = self.combo_box.currentData()

        # showing the role throw label
        self.label.setText(role)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396835-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200412025223/Python-12-04-2020-02_51_35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200412025223/Python-12-04-2020-02_51_35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200412025223/Python-12-04-2020-02_51_35.mp4)</video>