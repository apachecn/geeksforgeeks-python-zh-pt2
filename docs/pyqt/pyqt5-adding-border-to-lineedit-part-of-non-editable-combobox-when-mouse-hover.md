# PyQt5–鼠标悬停时为不可编辑组合框的 lineedit 部分添加边框

> 原文:[https://www . geesforgeks . org/pyqt 5-添加边框到线条编辑-部分不可编辑-鼠标悬停时组合框/](https://www.geeksforgeeks.org/pyqt5-adding-border-to-lineedit-part-of-non-editable-combobox-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在不可编辑的组合框上时，如何为其线条编辑部分设置边框。行编辑部分是组合框中显示所选项的部分，本质上是可编辑的。为了设置和访问线编辑对象，我们分别使用`setLineEdit`和`lineEdit`方法。

注意:当我们添加线编辑对象到组合框时，它使组合框可编辑，因此需要使线编辑对象不可编辑。

> 为此，我们必须执行以下操作:
> 
> 1.创建组合框
> 2。向组合框
> 3 添加项目。创建一个 QLineEdit 对象
> 4。使线编辑对象不可编辑
> 5。鼠标悬停在 QLineEdit 对象上时，为其设置边框
> 6。将 QLineEdit 对象添加到组合框中

**语法:**

```
# creating line edit object
line_edit = QLineEdit()

# making line edit non editable
line_edit.setReadOnly(True)

# setting border to the line edit when mouse hover over it
line_edit.setStyleSheet("QLineEdit::hover"
                        "{"
                        "border : 2px solid green;"
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
        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating line edit object
        line_edit = QLineEdit()

        # making line edit non editable
        line_edit.setReadOnly(True)

        # setting border to the line edit when mouse hover over it
        line_edit.setStyleSheet("QLineEdit::hover"
                                "{"
                                "border : 2px solid green;"
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

<video class="wp-video-shortcode" id="video-400144-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200419232226/Python-19-04-2020-23_12_36.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200419232226/Python-19-04-2020-23_12_36.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200419232226/Python-19-04-2020-23_12_36.mp4)</video>