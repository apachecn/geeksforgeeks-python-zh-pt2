# PyQt5–获取组合框

中所选项目的当前索引

> 原文:[https://www . geeksforgeeks . org/pyqt 5-获取组合框中选定项目的当前索引/](https://www.geeksforgeeks.org/pyqt5-getting-the-current-index-of-selected-item-in-combobox/)

在本文中，我们将看到如何获取组合框中所选项的当前索引。为了做到这一点，我们将使用`currentIndex`方法。

> **语法:**combo _ box . CurrentDex()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数，即所选项目的索引

**实施步骤–**

1.创建一个组合框
2。向组合框
3 添加项目。创建按钮
4。向按钮
5 添加动作。创建标签以显示计数
5。在动作内部，借助`currentIndex`方法获取在组合框中选择的当前项目的索引，并将其存储在变量
6 中。借助`setText`方法在标签中显示索引。

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

        # finding the current item index  in combo box
        index = self.combo_box.currentIndex()

        # showing content on the screen though label
        self.label.setText("Index : " + str(index))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396211-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200410234807/Python-10-04-2020-23_45_59.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200410234807/Python-10-04-2020-23_45_59.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200410234807/Python-10-04-2020-23_45_59.mp4)</video>