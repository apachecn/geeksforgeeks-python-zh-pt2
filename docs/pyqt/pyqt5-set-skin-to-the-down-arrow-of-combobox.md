# PyQt5–将皮肤设置为组合框的向下箭头

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置皮肤向下箭头的组合框/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-the-down-arrow-of-combobox/)

在本文中，我们将看到如何将皮肤设置为组合框的向下箭头。向下箭头是组合框的按钮部分，按下该按钮可打开列表视图。下面是下拉箭头外观的图示。

![](img/3dd233e3153952052999b11e818a0dd1.png)

为此，我们必须更改与组合框关联的样式表代码，下面是样式表代码

```
QComboBox::down-arrow
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
        # adding skin to drop down arrow
        self.combo_box.setStyleSheet("QComboBox::down-arrow"
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
![](img/5ccf273cb244f583a57209e9e9c9dfe3.png)