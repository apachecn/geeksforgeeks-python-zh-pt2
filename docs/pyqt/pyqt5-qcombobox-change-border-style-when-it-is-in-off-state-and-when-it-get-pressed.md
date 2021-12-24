# PyQt5 QComboBox–关闭状态和按下时改变边框样式

> 原文:[https://www . geesforgeks . org/pyqt 5-qcombobox-change-border-style-处于关闭状态时和按下时/](https://www.geeksforgeeks.org/pyqt5-qcombobox-change-border-style-when-it-is-in-off-state-and-when-it-get-pressed/)

在这篇文章中，我们将看到当组合框处于关闭状态并被按下时，我们如何改变它的边框样式，边框样式可以是点状、虚线等。当我们为组合框设置边框时，它是连续的，尽管我们可以更改它。只有当组合框处于关闭状态且被按下时，样式化的边框才可见，否则正常的边框将可见。

为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码

```py
QComboBox::!on:pressed
{
border : 4px black;
border-style : dotted;
}

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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 100, 40)

        # making combo box editable
        # self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting stylesheet of the combo box
        # set the border style when it is in off state
        # and get pressed
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : 4px solid black"
                                     "}"
                                     "QComboBox::! on:pressed"
                                     "{"
                                     "border : 4px black;"
                                     "border-style : dotted;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410653-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200509024714/Python-09-05-2020-02_46_52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200509024714/Python-09-05-2020-02_46_52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200509024714/Python-09-05-2020-02_46_52.mp4)</video>