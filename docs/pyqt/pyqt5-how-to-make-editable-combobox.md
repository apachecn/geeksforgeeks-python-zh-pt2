# PyQt5–如何制作可编辑的组合框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-如何编辑-combobox/](https://www.geeksforgeeks.org/pyqt5-how-to-make-editable-combobox/)

在本文中，我们将看到如何创建一个组合框，这样用户就可以通过键入来改变它的值。默认情况下，当我们创建一个组合框时，我们只能从下拉菜单中选择选项，尽管在可编辑的组合框中，我们可以自己设置文本。

为了做到这一点，我们将使用`setEditable`方法

> **语法:**组合框.设置可编辑(真)
> 
> **自变量:**它以布尔为自变量
> 
> **执行的操作:**组合框可编辑

下面是实现

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

        # creating a editable combo box
        self.combo_box.setEditable(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396247-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200411023233/Python-11-04-2020-02_30_59.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200411023233/Python-11-04-2020-02_30_59.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200411023233/Python-11-04-2020-02_30_59.mp4)</video>