# PyQt5 组合框–鼠标悬停时线条编辑部分的不同边框宽度

> 原文:[https://www . geesforgeks . org/pyqt 5-组合框-不同边框宽度到线条编辑-鼠标悬停部分/](https://www.geeksforgeeks.org/pyqt5-combo-box-different-border-width-to-lineedit-part-on-mouse-hover/)

在本文中，我们将看到当鼠标悬停在线编辑部分上时，如何为组合框的线编辑部分设置不同的边框宽度，线编辑是组合框中显示选定项目的部分，它本质上是可编辑的。为了设置和访问线编辑对象，我们分别使用`setLineEdit`和线编辑方法。

> 为此，我们必须执行以下操作:
> 
> 1.创建组合框
> 2。向组合框
> 3 添加项目。创建一个 QLineEdit 对象
> 4。为 QLineEdit 对象设置边框
> 5。鼠标悬停在边框上时设置不同宽度的边框
> 6。将 QLineEdit 对象添加到组合框中

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
        # set different border width when mouse hover over it
        line_edit.setStyleSheet("QLineEdit"
                                "{"
                                "border : 2px solid black"
                                "}"
                                "QLineEdit::hover"
                                "{"
                                "border : solid black;"
                                "border-width : 1px 10px 2px 5px;"
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

<video class="wp-video-shortcode" id="video-407339-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200504012339/Python-04-05-2020-01_21_26.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200504012339/Python-04-05-2020-01_21_26.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200504012339/Python-04-05-2020-01_21_26.mp4)</video>