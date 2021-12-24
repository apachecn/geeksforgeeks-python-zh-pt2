# PyQt5 QSpinBox–获取原生父小部件

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-native-parent-widget/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-native-parent-widget/)

在本文中，我们将看到如何获得旋转框的原生父小部件。原生父小部件是具有系统标识符的下一个祖先小部件，如果它没有任何原生父小部件，则为空值。

为了做到这一点，我们对旋转框对象使用`nativeParentWidget`方法。

> **语法:** spin_box.nativeParentWidget()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QWidget 对象，但如果没有父对象，则返回 Null

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

        # setting range to the spin box
        self.spin.setRange(1, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # creating a label
        label = QLabel(self)

        # making the label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting native parent widget
        value = self.spin.nativeParentWidget()

        # setting text to the label
        label.setText("Native parent widget  : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/77b345758b8fdf2ac6393eeb6ec066b7.png)