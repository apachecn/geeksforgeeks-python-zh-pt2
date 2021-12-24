# PyQt5 QdoubleSpinbox–获取对其的线编辑

> 原文:[https://www . geesforgeks . org/pyqt5-qdoublespinbox-get-line-edit-of-it/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-getting-line-edit-of-it/)

在本文中，我们将看到如何获得 QDoubleSpinBox 的行编辑。线编辑是接收输入并显示双旋转框当前值的空白，我们可以借助`setLineEdit`方法随时更改线编辑对象。线编辑是双旋转框的主要组成部分。默认的线编辑是这样进行的，它只接收浮点值。

> 为了做到这一点，我们将使用双旋转框对象的`lineEdit`方法。
> 
> **语法:** dd_spin.lineEdit()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QLineEdit 对象

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating double spin box
        d_spin = QDoubleSpinBox(self)

        # setting geometry to the double spin box
        d_spin.setGeometry(100, 100, 150, 40)

        # setting decimal precision
        d_spin.setDecimals(1)

        # step type
        step_type = QAbstractSpinBox.AdaptiveDecimalStepType

        # adaptive step type
        d_spin.setStepType(step_type)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting line edit
        value = d_spin.lineEdit()

        # setting text to the label
        label.setText("Line Edit : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/9719fb8de6a89e8eadc5971ec73ea1ab.png)