# PyQt5 组合框–不同边框颜色

> 原文:[https://www . geesforgeks . org/pyqt 5-组合框-不同边框-颜色/](https://www.geeksforgeeks.org/pyqt5-combo-box-different-border-color/)

在本文中，我们将看到如何为组合框创建一个多色边框，当我们为组合框设置边框时，它对所有墙壁都是相同的颜色，尽管我们可以分别更改它的颜色。下面是多色边框外观的图示–

![](img/3b880e2404384405ac35bdba583b9baf.png)

为此，我们必须更改与组合框关联的样式表，下面是样式表代码

```
QComboBox
{
border : 5px solid;
border-color : red yellow green black;
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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet
        self.combo_box.setStyleSheet("QComboBox"
                                     "{"
                                     "border : 5px solid;"
                                     "border-color : red yellow green black;"
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
![](img/92b5113c5280b9f332bc39e415ea46fb.png)