# PyQt5 组合框–鼠标悬停在关闭状态时不同的边框尺寸

> 原文:[https://www . geeksforgeeks . org/pyqt 5-combobox-不同边框大小-处于关闭状态时-鼠标悬停时-it/](https://www.geeksforgeeks.org/pyqt5-combobox-different-border-size-when-it-is-in-off-state-when-mouse-hover-it/)

在本文中，我们将看到当组合框处于关闭状态并且鼠标悬停在其上时，我们如何为组合框设置不同的边框宽度，当我们为组合框设置边框时，它对所有边都是相同的宽度虽然我们可以分别更改每个边的宽度，但是不同宽度的边框只会在组合框处于关闭状态并且光标在组合框上时出现，否则它将显示正常的边框。关闭状态指项目视图未打开时的状态。

为此，我们必须更改与组合框相关联的样式表，下面是样式表代码
**代码 1**

```
QComboBox::!on:hover
{
border : solid black;
border-width-top : 1px;
border-width-right : 5px;
border-width-bottom : 2px;
border-width-left : 10px;
}

```

**代码 2**

```
QComboBox::!on:hover
{
border : solid black;
border-width : 1px 5px 2px 10px;
}

```

这两个代码执行类似的任务，只是代码 1 是代码 2 的扩展版本。

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

        # setting style sheet
        # adding border to combo box
        # adding different width border when it is OFF and mouse hover over it
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : 5px solid black;"
                                     "}"
                                     "QComboBox::! on:hover"
                                     "{"
                                     "border : solid black;"
                                     "border-width : 1px 5px 2px 10px;;"                                     
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

<video class="wp-video-shortcode" id="video-404540-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200428013204/Python-28-04-2020-01_31_37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200428013204/Python-28-04-2020-01_31_37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200428013204/Python-28-04-2020-01_31_37.mp4)</video>