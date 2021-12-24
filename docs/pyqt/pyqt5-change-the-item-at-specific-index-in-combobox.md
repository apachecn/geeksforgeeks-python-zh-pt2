# PyQt5–在组合框

中的特定索引处更改项目

> 原文:[https://www . geeksforgeeks . org/pyqt 5-在组合框中更改特定项目索引/](https://www.geeksforgeeks.org/pyqt5-change-the-item-at-specific-index-in-combobox/)

在本文中，我们将看到如何在组合框中的特定索引处更改项目的内容。为了做到这一点，我们将使用`setItemText`方法。

> **语法:**组合框. setItemText(索引，项目)
> 
> **参数:**需要两个参数，一个是整数，第二个是字符串
> 
> **执行的操作:**这将改变特定索引处的内容

**实施步骤–**

1.创建组合框
2。向组合框
3 添加项目。创建按钮
4。向按钮
5 添加动作。创建标签以显示先前的文本
5。在操作中，使用 setItemText 方法更改给定索引处的项目内容

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
        button = QPushButton("Change content ", self)

        print(self.combo_box.count())

        # adding action to button
        button.pressed.connect(self.find)

        # creating label
        self.label = QLabel(self)

        # setting geometry of the label
        self.label.setGeometry(200, 200, 200, 30)

        # old content at index 2
        content = self.combo_box.itemText(2)

        # showing the old content
        self.label.setText("old content  : content")

    def find(self):

        # index
        index = 2

        # changing the content
        self.combo_box.setItemText(index, "New data")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396213-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200411003353/Python-11-04-2020-00_30_51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200411003353/Python-11-04-2020-00_30_51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200411003353/Python-11-04-2020-00_30_51.mp4)</video>