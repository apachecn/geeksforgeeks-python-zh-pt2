# PyQt5 QDoubleSpinBox–获取全文

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-get-整篇-text/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-getting-whole-text/)

在本文中，我们将看到如何获得 QDoubleSpinBox 的整个文本。我们可以借助`value`方法获得双旋转框的当前值，但它只获得值，而不是前缀和后缀部分。完整文本意味着文本在双旋转框即前缀，价值和后缀都包括在内。

> 为了做到这一点，我们将使用双旋转框对象的`text`方法。
> 
> **语法:** dd_spin.text()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

        # setting suffix
        d_spin.setSuffix("value")

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

        # getting whole text
        value = d_spin.text()

        # setting text to the label
        label.setText("Text : " + value)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/a26961cd61a9c4bf89b80f8361590cfc.png)