# PyQt5 QDoubleSpinBox–步进

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qdoublespinbox-stepping-by/](https://www.geeksforgeeks.org/pyqt5-qdoublespinbox-stepping-by/)

在本文中，我们将看到如何通过编程来逐步确定 QDoubleSpinBox 的值。双尾旋框可以以十进制值作为输入，我们可以借助 set value 方法设置值，步进时会将定数加到当前值上它既可以是正数也可以是负数。

**注意:**如果选择了自适应类型，它会将小数部分的值加到实数部分。

> 为了做到这一点，我们将使用双旋转框对象的逐步方法。
> **语法:** dd_spin.stepBy(n)
> **参数:**以整数为参数
> **返回:**不返回

下面是实现

## 蟒蛇 3

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
        # stepping by the value by 5
        push.clicked.connect(lambda: d_spin.stepBy(5))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-455798-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200720021036/Python-2020-07-20-02-10-19.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200720021036/Python-2020-07-20-02-10-19.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200720021036/Python-2020-07-20-02-10-19.mp4)</video>