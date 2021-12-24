# PyQt5 QDoubleSpinBox–获得小数精度

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-get-decimal-precision/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-getting-decimal-precision/)

在本文中，我们将了解如何获得 QDoubleSpinBox 的十进制精度。默认情况下，双旋转框的小数精度为 2，尽管我们可以借助`setDecimals`方法随时更改它。小数精度是数字中小数点右边的位数。例如，数字 123.45 的十进制精度为 2。

> 为了做到这一点，我们将使用双旋转框对象的`decimals`方法。
> 
> **语法:** dd_spin.decimals()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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
        d_spin.setDecimals(4)

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

        # getting decimal precision
        value = d_spin.decimals()

        # setting text to the label
        label.setText("Decimal Precision : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8fc80eca816bdb9d77cda367a36ebbba.png)