# pyqt 5–按下时将背景颜色设置为可编辑关闭状态组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景色-可编辑-关闭-状态-组合框-按下时/](https://www.geeksforgeeks.org/pyqt5-set-background-color-to-editable-off-state-combobox-when-pressed/)

在本文中，我们将看到如何设置当前处于打开状态的可编辑组合框的背景颜色，以及何时按下它。当列表菜单未打开时，组合框处于关闭状态。只有当组合框可编辑且处于关闭状态时，以及当组合框被按下时，此背景颜色才会出现。在`setEditable`方法的帮助下，组合框变得可编辑。

为此，我们必须更改样式表代码，下面是样式表代码

```
QComboBox::editable:!on:pressed
{
background-color : lightgreen;
}

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

        # making combo box editable
        self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # adding background color to the combo box when it is editable
        # and when it is in OFF state and it get pressed
        self.combo_box.setStyleSheet("QComboBox::editable:! on:pressed"
                                     "{"
                                     "background-color: lightgreen;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-399639-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200417003842/Python-17-04-2020-00_37_14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200417003842/Python-17-04-2020-00_37_14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200417003842/Python-17-04-2020-00_37_14.mp4)</video>