# PyQt5 QDoubleSpinBox–设置步长类型属性

> 原文:[https://www . geesforgeks . org/pyqt 5-qdoublespinbox-设置-步骤-类型-属性/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-setting-step-type-property/)

在本文中，我们将看到如何设置 QDoubleSpinBox 的步长类型属性。此属性保存步骤类型。步长类型可以是单步或自适应十进制步长。默认情况下，当我们更改值时，它会按整数而不是十进制值进行更改，尽管我们可以借助 step-type 属性进行更改。

为了做到这一点，我们将使用`setStepType`方法和 QDateTimeEdit 对象。

> **语法:**DD _ spin . setsteptype(step _ type)
> 
> **自变量:**以步型对象为自变量
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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451450-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200713013624/Python-2020-07-13-01-36-03.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200713013624/Python-2020-07-13-01-36-03.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200713013624/Python-2020-07-13-01-36-03.mp4)</video>