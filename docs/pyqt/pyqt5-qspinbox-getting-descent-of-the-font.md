# PyQt5 QSpinBox–获得字体的下降

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-获得血统的字体/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-descent-of-the-font/)

在本文中，我们将看到如何获得旋转框的字体，即文本的下降。下降是从基线到字符延伸到的最低点的距离。在实践中，一些字体设计者打破了这一规则，例如，为了适应异国语言中的不寻常字符，因此该值可能(尽管很少)太小。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`descent`方法。

> **语法:**font _ metrics . decision()
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

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting descent value
        descent = f_metrics.descent()

        # setting text to the label
        label.setText("Descent : " + str(descent))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/fd55f80401195d0180860bc4e3e8e009.png)