# PyQt5 组合框–按下时的皮肤

> 原文:[https://www . geeksforgeeks . org/pyqt 5-组合框-皮肤-按下时/](https://www.geeksforgeeks.org/pyqt5-combo-box-skin-when-pressed/)

在本文中，我们将看到如何在组合框被按下时为其设置皮肤。皮肤基本上是背景图像，但皮肤根据组合框的大小调整其大小。皮肤只会在组合框被按下时出现。

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::pressed
{
border-image : url(image.png);
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
        self.combo_box.setGeometry(200, 150, 200, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of combo box
        # adding skin to the combo box when it get pressed
        self.combo_box.setStyleSheet("QComboBox::pressed"
                                     "{"
                                     "border-image : url(image.png);"
                                     "border : 1px solid black;"
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

<video class="wp-video-shortcode" id="video-401698-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423232736/Python-23-04-2020-23_26_58.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423232736/Python-23-04-2020-23_26_58.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423232736/Python-23-04-2020-23_26_58.mp4)</video>