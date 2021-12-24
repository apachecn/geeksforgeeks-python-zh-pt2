# PyQt5–将皮肤设置为组合框

> 原文:[https://www.geeksforgeeks.org/pyqt5-set-skin-to-combobox/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-combobox/)

在本文中，我们将看到如何为组合框设置皮肤。皮肤基本上是背景图像，但皮肤根据组合框的大小调整其大小。下面是皮肤组合框的外观。

![](img/970ab41df5ee7ef43f43559bf4efa161.png)

为此，我们必须更改组合框的样式表代码，下面是样式表代码–

```py
QComboBox
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

        # making combo box editable
        self.combo_box.setEditable(True)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 200, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of combo box
        # adding skin to the combo box
        self.combo_box.setStyleSheet("QComboBox"
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
![](img/2619d2a77f441ba5d66efe09b916ee77.png)