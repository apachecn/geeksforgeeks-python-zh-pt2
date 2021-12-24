# PyQt5–如何删除组合框中的所有项目？

> 原文:[https://www . geeksforgeeks . org/pyqt 5-如何删除组合框中的所有项目/](https://www.geeksforgeeks.org/pyqt5-how-to-delete-all-the-items-in-combobox/)

在本文中，我们将看到如何清除组合框中的所有项目。我们知道可以借助`addItem`方法增加单品，`addItems`方法增加多品，在组合框中增加物品。为了删除组合框中的所有项目，我们将使用`clear`方法。

> **语法:**组合框. clear()
> 
> **论证:**不需要论证
> 
> **执行动作:**删除组合框所有项目

**实施步骤:**

1.创建组合框
2。向组合框
3 添加项目。创建按钮
4。向按钮
5 添加动作。在清除方法的帮助下，删除组合框中的项目

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

        # creating push button to clear the list
        button = QPushButton("Clear", self)

        # adding action to button
        button.pressed.connect(self.delete)

    def delete(self):

        # delete items of list
        self.combo_box.clear()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396225-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200410225651/Python-10-04-2020-22_55_22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200410225651/Python-10-04-2020-22_55_22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200410225651/Python-10-04-2020-22_55_22.mp4)</video>