# PyQt5 QComboBox–将 lineedit 部分的边框样式更改为不可编辑状态，鼠标悬停

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcombobox-change-border-style-of-line edit-part-for-不可编辑-state-and-鼠标悬停/](https://www.geeksforgeeks.org/pyqt5-qcombobox-change-border-style-of-lineedit-part-for-non-editable-state-and-mouse-hover/)

在本文中，我们将看到当鼠标悬停在不可编辑的组合框上时，如何将边框样式更改为该组合框的线条编辑部分，线条编辑是组合框中显示选定项目的部分，它本质上是可编辑的。为了设置和访问线编辑对象，我们分别使用`setLineEdit`和`lineEdit`方法。反悬停状态是当鼠标不在组合框上时。

**注意:**当我们创建线编辑对象时，它使组合框可编辑，因此需要停止线编辑来接收输入。

> 为此，我们必须执行以下操作:
> 
> 1.创建组合框
> 2。向组合框
> 3 添加项目。创建一个 QLineEdit 对象
> 4。将边框设置为 QLineEdit 对象
> 5。鼠标悬停在其上时添加边框样式
> 6。使其只读
> 7。将 QLineEdit 对象添加到组合框中

**语法:**

```
# creating line edit object
line_edit = QLineEdit()

# setting border to the line edit part
# set border style
line_edit.setStyleSheet("QLineEdit::hover"
                        "{"
                        "border : 4px black;"
                        "border-style : dotted;"
                        "}")

# making line edit non editable
line_edit.setReadOnly(True)

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
        # set border style when mouse hover over it 
        line_edit.setStyleSheet("QLineEdit"
                                "{"
                                "border : 4px solid black;"
                                "}"
                                "QLineEdit::hover"
                                "{"
                                "border-style : dashed;"
                                "}")

        # making line edit non editable
        line_edit.setReadOnly(True)

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

<video class="wp-video-shortcode" id="video-411151-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512041952/Python-12-05-2020-04_19_34.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512041952/Python-12-05-2020-04_19_34.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512041952/Python-12-05-2020-04_19_34.mp4)</video>