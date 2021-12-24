# PyQt5–鼠标悬停时线条编辑组合框部分的背景图像

> 原文:[https://www . geeksforgeeks . org/pyqt 5-bbbackground-image-to-line edit-part-combobox-当鼠标悬停时/](https://www.geeksforgeeks.org/pyqt5-bbackground-image-to-lineedit-part-of-combobox-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在组合框上时，如何将背景图像设置到组合框的线条编辑部分。行编辑是组合框的一部分，用于查看选定的文本和编辑文本。为了设置和获取组合框的行编辑对象，我们使用了设置行编辑和行编辑方法。
为了做到这一点，我们必须做以下工作

> 1.创建组合框
> 2。向组合框
> 3 添加项目。创建一个 QLineEdit 对象
> 4。鼠标悬停在 QLineEdit 对象上时，为其添加背景图像
> 5。将线条编辑对象添加到组合框

**语法:**

```
# creating line edit object
line_edit = QLineEdit()

# setting style sheet of line edit
# adding background image when mouse hover over it
line_edit.setStyleSheet("QLineEdit::hover"
                        "{"
                        "background-image : url(logo.png);"
                        "border : 2px solid black;"
                        "}")

# adding line edit to the combo box
combo_box.setLineEdit(line_edit)
```

下面是实现

## 蟒蛇 3

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

        # making combo box editable
        self.combo_box.setEditable(True)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 200, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating line edit object
        line_edit = QLineEdit()

        # setting style sheet of line edit
        # adding background image when mouse hover over it
        line_edit.setStyleSheet("QLineEdit::hover"
                                "{"
                                "background-image : url(logo.png);"
                                "border : 2px solid black;"
                                "}")

        # adding line edit to the combo box
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

<video class="wp-video-shortcode" id="video-401648-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423002308/Python-23-04-2020-00_22_51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423002308/Python-23-04-2020-00_22_51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423002308/Python-23-04-2020-00_22_51.mp4)</video>