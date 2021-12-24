# PyQt5–按下时将皮肤设置为组合框的向下箭头

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置皮肤向下箭头的组合框-按下时/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-the-down-arrow-of-combobox-when-pressed/)

在本文中，我们将看到如何在组合框被按下时将皮肤设置为向下箭头。向下箭头是组合框的按钮部分，按下该按钮可打开列表视图。只有当向下箭头被按下时，皮肤才会出现。

为此，我们必须更改与组合框关联的样式表代码，下面是样式表代码

```
QComboBox::down-arrow::pressed
{
border-image : url(image.png);
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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 200, 80)

        # making combo box editable
        # self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet to the combo box
        # adding skin to drop down arrow when it get pressed
        self.combo_box.setStyleSheet("QComboBox::down-arrow:pressed"
                                     "{"
                                     "border-image : url(image.png);"
                                     "border : 1px solid black;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-402543-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200424131513/Python-24-04-2020-13_14_52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200424131513/Python-24-04-2020-13_14_52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200424131513/Python-24-04-2020-13_14_52.mp4)</video>