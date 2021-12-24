# PyQt5–将工具提示设置到组合框

的视图(下拉)部分

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-工具-提示-查看-下拉-组合框的一部分/](https://www.geeksforgeeks.org/pyqt5-setting-tool-tip-to-the-view-drop-down-part-of-combobox/)

在本文中，我们将看到如何将工具提示设置到组合框的下拉部分。当我们将工具提示设置为组合框时，它只显示线编辑部分，工具提示对于下拉部分(即其视图部分)不可见。

> **为了将工具提示设置到视图部分，我们必须执行以下操作–**
> 
> 1.创建组合框
> 2。向组合框
> 3 添加项目。获取组合框
> 4 的视图对象。向视图对象添加工具提示

**语法:**

```py
# getting view part of combo box
view = self.combo_box.view()

# setting tool tip to view object of the combo box
view.setToolTip(tip)

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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # making it editable
        self.combo_box.setEditable(True)

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # tool tip
        tip = "Drop down tool tip"

        # getting view part of combo box
        view = self.combo_box.view()

        # setting tool tip to view object of the combo box
        view.setToolTip(tip)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/3907cf130a3c4b69789adaced26b22f0.png)