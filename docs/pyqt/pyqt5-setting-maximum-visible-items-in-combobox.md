# PyQt5–在组合框中设置最大可见项目数

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置-最大可见-组合框中的项目/](https://www.geeksforgeeks.org/pyqt5-setting-maximum-visible-items-in-combobox/)

在本文中，我们将看到如何设置组合框的最大可见项目。默认情况下，在组合框下拉列表中一次最多可以看到 10 个项目，尽管我们可以更改这个数字。

为了改变最大可见项目数，我们使用`setMaxVisibleItems`方法。

> **语法:**组合框. setMaxVisibleItems(n)
> 
> **自变量:**以整数为自变量
> 
> **执行的操作:**将设置可见项目的最大数量

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
        self.combo_box.setGeometry(200, 150, 120, 30)

        # geek list
        geek_list = ["Geek", "Geeky Geek", "Legend Geek", "Ultra Legend Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting max number visible limit
        self.combo_box.setMaxVisibleItems(2)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396711-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200411185525/Python-11-04-2020-18_53_16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200411185525/Python-11-04-2020-18_53_16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200411185525/Python-11-04-2020-18_53_16.mp4)</video>