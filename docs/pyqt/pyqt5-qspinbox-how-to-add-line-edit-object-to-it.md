# PyQt5 QSpinbox–如何向其添加线编辑对象

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-如何添加行-编辑-对象到它/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-add-line-edit-object-to-it/)

在本文中，我们将看到如何向旋转框中添加线编辑对象，线编辑是 PyQt5 中的小部件，用于显示文本和接受输入文本。默认情况下，旋转框有自己的线编辑对象，虽然我们可以添加自己的线编辑对象。

> 为此，我们使用了 setLineEdit 方法
> 
> **语法:**旋转框。设置线编辑(线编辑对象)
> 
> **参数:**以行编辑对象为参数
> 
> **返回:**返回无

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # creating a line edit object
        line = QLineEdit(self)

        # adding this line edit to the spin box
        self.spin.setLineEdit(line)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8d3d9993a81cd948defe0156ed57efb2.png)