# PyQt5–如何在组合框

中进行重复插入

> 原文:[https://www . geeksforgeeks . org/pyqt 5-如何制作副本-插入组合框/](https://www.geeksforgeeks.org/pyqt5-how-make-duplicates-insertions-in-combobox/)

在本文中，我们将看到如何在组合框中允许重复插入。默认情况下，不允许重复插入，尽管可以通过编程方式将重复项插入组合框，但用户不能插入重复值。

为了允许重复插入，我们将使用`setDuplicatesEnabled`方法

> **语法:**组合框。设置重复呈现(真)
> 
> **自变量:**它以布尔为自变量
> 
> **执行的操作:**允许用户重复插入

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
        geek_list = ["Geek", "Geeky Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # making it editable combo box
        self.combo_box.setEditable(True)

        # allowing duplication of items
        # setting duplicates = True
        self.combo_box.setDuplicatesEnabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396827-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200412023029/screen_recorder_video_2020_12_4_02_29_14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200412023029/screen_recorder_video_2020_12_4_02_29_14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200412023029/screen_recorder_video_2020_12_4_02_29_14.mp4)</video>