# PyQt5 组合框–按下时不同的边框尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-combobox-不同边框-尺寸-按下时/](https://www.geeksforgeeks.org/pyqt5-combobox-different-border-sizes-when-pressed/)

在本文中，我们将看到如何在组合框被按下时为其设置不同的边框大小，当我们为组合框设置边框时，尽管我们可以分别更改每条边的宽度，但所有边的边框大小都是相同的。只有在按下组合框时才会出现不同的边框，否则正常的边框将可见

为此，我们必须更改与组合框相关联的样式表，下面是样式表代码
**代码 1**

```py
QComboBox::pressed
{
border : solid black;
border-width-top : 1px;
border-width-right : 5px;
border-width-bottom : 2px;
border-width-left : 10px;
}

```

**代码 2**

```py
QComboBox::pressed
{
border : solid black;
border-width : 1px 5px 2px 10pxk
}

```

这两个代码执行类似的任务，只是代码 1 是代码 2 的扩展版本。

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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet
        # adding border to combo box
        # adding different width border when it get pressed
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : 5px solid black;"
                                     "}"
                                     "QComboBox::pressed"
                                     "{"
                                     "border : solid black;"
                                     "border-width : 1px 5px 2px 10px;"
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

<video class="wp-video-shortcode" id="video-404025-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200427023746/Python-27-04-2020-02_37_32.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200427023746/Python-27-04-2020-02_37_32.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200427023746/Python-27-04-2020-02_37_32.mp4)</video>