# PyQt5 QDoubleSpinBox–清洁文本

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-cleaning-text/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-cleaning-text/)

在本文中，我们将看到如何清理 QDoubleSpinBox 的文本。我们可以在 clean text 属性的帮助下清理文本，该属性保存旋转框的文本，不包括任何前缀、后缀、前导或尾随空格。

> 为了做到这一点，我们将使用双旋转框对象的`cleanText`方法。
> 
> **语法:** dd_spin.cleanText()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

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

        # setting suffix
        d_spin.setSuffix(" value")

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

        # push button
        push = QPushButton("Press", self)

        # setting geometry to the push button
        push.setGeometry(100, 150, 100, 35)

        # adding action to the push button
        # showing clean text
        push.clicked.connect(lambda: label.setText(d_spin.cleanText()))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-455804-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200720022125/Python-2020-07-20-02-21-03.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200720022125/Python-2020-07-20-02-21-03.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200720022125/Python-2020-07-20-02-21-03.mp4)</video>