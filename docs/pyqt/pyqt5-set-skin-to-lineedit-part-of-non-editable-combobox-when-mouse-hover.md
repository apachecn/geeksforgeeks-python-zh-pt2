# PyQt5–鼠标悬停时将皮肤设置为不可编辑组合框的线编辑部分

> 原文:[https://www . geesforgeks . org/pyqt 5-set-skin-to-line edit-部分不可编辑-combobox-当鼠标悬停时/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-lineedit-part-of-non-editable-combobox-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在不可编辑的组合框上时，如何为其线条编辑部分设置皮肤。行编辑是用于输入和查看项目的部分。皮肤基本上是根据线条编辑的大小来调整自身的背景图像。

**注意:**当我们在组合框中添加线编辑对象时，它会使组合框可编辑，但需要使其不可编辑

**这样做的步骤:**
1。创建组合框
2。创建一个 QLineEdit 对象
3。鼠标悬停在 QlineEdit 对象上时，为其设置皮肤
4。使线编辑不可编辑
5。将 QLineEdit 对象添加到组合框中

**语法:**

```
# creating line edit object
line_edit = QLineEdit()

# setting skin to line edit when mouse hover over it
line_edit.setStyleSheet("QLineEdit::hover"
                        "{"
                        "border-image : url(skin.png);"
                        "}")

# making it non editable
line_edit.setReadOnly(True)

# adding line edit object to combo box
combo_box.setLineEdit(line_edit)

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

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating line edit object
        line_edit = QLineEdit()

        # setting skin to line edit when mouse hover over it
        line_edit.setStyleSheet("QLineEdit::hover"
                                "{"
                                "border-image : url(skin.png);"
                                "}")

        # making it non editable
        line_edit.setReadOnly(True)

        # adding line edit object to combo box
        self.combo_box.setLineEdit(line_edit)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-402549-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200424134949/Python-24-04-2020-13_47_06.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200424134949/Python-24-04-2020-13_47_06.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200424134949/Python-24-04-2020-13_47_06.mp4)</video>