# PyQt5–如果按下

，组合框关闭状态的背景颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-背景色到组合框-关闭状态-如果按下/](https://www.geeksforgeeks.org/pyqt5-background-color-to-combobox-off-state-if-pressed/)

在本文中，我们将看到当组合框处于关闭状态并被按下时，我们如何设置它的背景色。默认情况下，组合框是灰色的，尽管我们可以更改它的颜色。此背景色仅在组合框小部件处于关闭状态且被按下时出现。下拉菜单未打开时，组合框处于关闭状态。

为此，我们必须更改组合框的样式表代码，下面是样式表代码–

```
QComboBox::!on:pressed
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

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # adding background color to the combo box when it is in OFF state
        # and when it get pressed
        self.combo_box.setStyleSheet("QComboBox::! on:pressed"
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

<video class="wp-video-shortcode" id="video-398541-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200416190209/Python-16-04-2020-18_56_46.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200416190209/Python-16-04-2020-18_56_46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200416190209/Python-16-04-2020-18_56_46.mp4)</video>