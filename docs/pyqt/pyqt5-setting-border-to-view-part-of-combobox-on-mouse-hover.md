# PyQt5–设置边框以在鼠标悬停时查看组合框的一部分

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-边框到视图-鼠标悬停组合框的一部分/](https://www.geeksforgeeks.org/pyqt5-setting-border-to-view-part-of-combobox-on-mouse-hover/)

在本文中，我们将看到当鼠标悬停在视图部分上时，如何为组合框的视图部分设置边框。视图部分基本上是下拉项列表，里面显示了所有可用的项，我们要借助`view`方法得到视图对象，默认情况下组合框使用 QListView 对象。

为了做到这一点，我们必须更改与组合框相关联的样式表，下面是实现这一点的样式表代码

```
QListView::hover
{
border : 3px solid red;
background : white;
}

```

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
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # editing style sheet code of combo box
        # adding border to the list view when mouse hover over it
        self.combo_box.setStyleSheet("QListView:hover"
                                     "{"
                                     "border : 3px solid red;"
                                     "background : white;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
当鼠标悬停在视图部分时，它将看起来像这样
![](img/23578a26e7bbbcac751a37f888dd8715.png)