# PyQt5–制作胶囊形组合框

> 原文:[https://www . geesforgeks . org/pyqt5-制作-胶囊形-组合框/](https://www.geeksforgeeks.org/pyqt5-making-capsule-shaped-combo-box/)

在本文中，我们将看到如何创建胶囊形状的组合框，组合框小部件不同于其他小部件，它由许多其他小部件组成，例如，文本视图、按钮、行编辑等。

为了使组合框循环，我们必须更改与组合框关联的样式表，下面是样式表代码

```
QComboBox
{
border : 1px solid black;
border-radius : 20px;

```

**备注:**

*   高度应小于宽度，边框半径应为高度的一半
*   它只使组合框主窗口小部件，即文本视图部分循环，它对按钮没有影响。

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
        self.combo_box.setGeometry(200, 150, 100, 40)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting stylesheet of the combo box
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : 1px solid black;"
                                     "border-radius : 20px;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/902ae00c0ea52252ba4235f66a423078.png)