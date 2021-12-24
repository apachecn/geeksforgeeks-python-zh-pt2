# PyQt5 QSpinBox–获取风格提示

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-style-hint/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-style-hint/)

在本文中，我们将看到如何获得旋转框文本的样式提示。如果选定的字体系列不可用，字体匹配算法将使用样式提示来查找合适的默认系列。旋转框提供了许多风格提示，如 AnyStyle、SansSerif、Times 等。我们可以借助`setStyleHint`方法将样式提示设置到旋转框中。

为了做到这一点，我们对旋转框的 QFont 对象使用`styleHint`方法。

> **语法:** font.styleHint()
> 
> **论证:**不需要论证
> 
> **Return :** 它返回 QFont 的 Style 提示对象，但打印出来后会显示与之关联的值

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting range to the spin box
        self.spin.setRange(0, 999999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # getting font of the spin box
        font = self.spin.font()

        # setting style hint
        font.setStyleHint(QFont.Serif, QFont.PreferOutline)

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting style hint
        style_hint = font.styleHint()

        # setting text to the label
        label.setText("Style Hint value: " + str(style_hint))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/cb21f835828f4da8475ac31bcc4c7b9f.png)