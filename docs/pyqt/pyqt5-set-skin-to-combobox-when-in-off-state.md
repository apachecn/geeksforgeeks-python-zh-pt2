# PyQt5–在关闭状态下将皮肤设置为组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-set-skin-to-combobox-处于关闭状态时/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-combobox-when-in-off-state/)

在本文中，我们将看到如何在组合框处于关闭状态时为其设置皮肤。关闭状态基本上是列表视图部分没有打开的时候。皮肤是根据组合框的大小自行调整的背景图像。只有当组合框列表视图(项目视图)部分未打开时，皮肤才会出现在组合框中。

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::!on
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

        # making combo box editable
        # self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of combo box
        # adding skin to the combo box when it is in OFF state
        self.combo_box.setStyleSheet("QComboBox::! on"
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