# PyQt5 组合框–按下时与向下箭头不同的边框尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-combobox-不同边框-大小-向下箭头-按下时/](https://www.geeksforgeeks.org/pyqt5-combobox-different-border-size-to-down-arrow-when-pressed/)

在本文中，我们将看到如何在向下箭头被按下时为其设置不同的大小/宽度边框，基本上，当我们将边框设置为向下箭头时，尽管我们可以更改其颜色，但所有边的宽度都是相同的。

为此，我们必须更改与组合框关联的样式表，下面是样式表代码–
**代码 1**

```py
QComboBox::down-arrow:pressed
{
border : solid black;
border-width-top : 5px;
border-width-right : 1px;
border-width-bottom : 10px;
border-width-left : 3px;
}

```

**代码 2**

```py
QComboBox::down-arrow:pressed
{
border : solid black;
border-width : 5px 1px 10px 3px;
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

        # making combo box editable
        self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet
        # adding to down arrow
        # adding different border width it get pressed
        self.combo_box.setStyleSheet("QComboBox::down-arrow"
                                     "{"
                                     "border : 1px solid black;"
                                     "}"
                                     "QComboBox::down-arrow:pressed"
                                     "{"
                                     "border : solid black;"
                                     "border-width : 5px 1px 10px 3px;"
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

<video class="wp-video-shortcode" id="video-406257-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200501020408/Python-01-05-2020-02_03_53.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200501020408/Python-01-05-2020-02_03_53.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200501020408/Python-01-05-2020-02_03_53.mp4)</video>