# PyQt5–在组合框

中获取特定索引处的项目内容

> 原文:[https://www . geeksforgeeks . org/pyqt 5-获取特定项目内容索引-in-combobox/](https://www.geeksforgeeks.org/pyqt5-getting-the-content-of-item-at-specific-index-in-combobox/)

在本文中，我们将看到如何在组合框中的特定索引处获取项目的内容。为了做到这一点，我们将使用`itemText`方法。

> **语法:**组合框.项目文本(索引)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回字符串，即项目内容

**实施步骤–**

1.创建组合框
2。向组合框
3 添加项目。创建按钮
4。向按钮
5 添加动作。创建标签以显示内容
5。在动作内部，借助 itemIndex 方法获取组合框中特定索引的内容，并存储在变量
6 中。借助 setText 方法在标签中显示内容。

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

        # creating push button
        button = QPushButton("Show content ", self)

        print(self.combo_box.count())

        # adding action to button
        button.pressed.connect(self.find)

        # creating label
        self.label = QLabel(self)

        # setting geometry of the label
        self.label.setGeometry(200, 200, 200, 30)

    def find(self):

        # index
        index = 2

        # finding the content at index  in combo box
        content = self.combo_box.itemText(index)

        # showing content on the screen though label
        self.label.setText("Content at index 2: " + content)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396709-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200411000948/Python-11-04-2020-00_07_38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200411000948/Python-11-04-2020-00_07_38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200411000948/Python-11-04-2020-00_07_38.mp4)</video>