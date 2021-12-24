# PyQt5–将背景颜色设置为鼠标悬停时不可编辑组合框的线条编辑

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置-背景-颜色到线条编辑-不可编辑-鼠标悬停组合框/](https://www.geeksforgeeks.org/pyqt5-set-background-color-to-lineedit-of-non-editable-combobox-on-mouse-hover/)

在本文中，我们将看到当鼠标悬停在不可编辑的组合框上时，我们如何为其线条编辑部分设置背景颜色，组合框的线条编辑部分是显示和编辑文本的地方。

**注意:**当我们在组合框中添加行编辑对象时，它会使组合框可编辑，因此需要使行编辑不可编辑。

> 为了在鼠标悬停在组合框的线条编辑部分时为其添加背景色，请执行以下操作–
> 
> 1.创建组合框
> 2。创建线编辑小部件
> 3。将鼠标悬停在线条编辑小部件上可更改其背景颜色
> 4。使线编辑不可编辑
> 5。将行编辑小部件添加到组合框中

**语法:**

```py
# creating line edit widget
line_edit = QLineEdit()

# setting background color to the line edit widget
line_edit.setStyleSheet("QLineEdit::hover"
                        "{"
                        "background : lightblue;"
                        "}")

# making line edit non editable
line_edit.setReadOnly(True)

# adding line edit widget to combo box
self.combo_box.setLineEdit(line_edit)

```

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
        self.combo_box.setGeometry(200, 150, 150, 30)

        # making combo box editable
        self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating line edit widget
        line_edit = QLineEdit()

        # setting background color to the line edit widget
        # when mouse hover over it
        line_edit.setStyleSheet("QLineEdit"
                                "{"
                                "background : lightblue;"
                                "}")

        # making line edit non editable
        line_edit.setReadOnly(True)

        # adding line edit widget to combo box
        self.combo_box.setLineEdit(line_edit)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-399709-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200417234904/Python-17-04-2020-23_47_59.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200417234904/Python-17-04-2020-23_47_59.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200417234904/Python-17-04-2020-23_47_59.mp4)</video>