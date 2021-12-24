# PyQt5 QComboBox–更改线条编辑部分的边框样式

> 原文:[https://www . geesforgeks . org/pyqt5-qcombobox-change-border-line-style-edit-part/](https://www.geeksforgeeks.org/pyqt5-qcombobox-change-border-style-of-line-edit-part/)

在本文中，我们将看到如何将边框样式更改为组合框的线条编辑部分，线条编辑是组合框中显示选定项目的部分，它本质上是可编辑的。为了设置和访问线编辑对象，我们分别使用`setLineEdit`和`lineEdit`方法。

**注意:**当我们创建线编辑对象时，它使组合框可编辑。

> 为此，我们必须执行以下操作:
> 
> 1.创建组合框
> 2。向组合框
> 3 添加项目。创建一个 QLineEdit 对象
> 4。将边框设置为 QLineEdit 对象
> 5。添加边框样式
> 6。将 QLineEdit 对象添加到组合框中

**语法:**

```
# creating line edit object
line_edit = QLineEdit()

# setting border to the line edit part
# set border style
line_edit.setStyleSheet("QLineEdit"
                        "{"
                        "border : 4px black;"
                        "border-style : dotted;"
                        "}")

# adding line edit object to the combo box
self.combo_box.setLineEdit(line_edit)

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
        self.combo_box.setGeometry(200, 150, 150, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating line edit object
        line_edit = QLineEdit()

        # setting border to the line edit part
        # set border style
        line_edit.setStyleSheet("QLineEdit"
                                "{"
                                "border : 4px black;"
                                "border-style : dotted;"
                                "}")

        # adding line edit object to the combo box
        self.combo_box.setLineEdit(line_edit)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b7557a67d5420edb72b532ee9af3e577.png)