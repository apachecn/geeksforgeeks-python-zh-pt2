# PyQt5 QSpinBox–字体上升

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-get-the-ascent-of-font/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-ascent-of-the-font/)

在这篇文章中，我们将看到如何提升旋转框的字体，即文本。字体的上坡是从基线到字符延伸到的最高位置的距离。在实践中，一些字体设计者打破了这一规则，例如，当他们在一个字符的顶部放上一个以上的重音符号，或者在一种外来语言中容纳一个不寻常的字符时，因此这个值可能(尽管很少)太小。

为了做到这一点，我们对旋转框的 QFontMetrics 对象使用`ascent`方法。

> **语法:** font_metrics.ascents()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # creating a label
        label = QLabel(self)

        # making label multi line
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting font metrics
        f_metrics = self.spin.fontMetrics()

        # getting ascent
        ascent = f_metrics.ascent()

        # setting text to the label
        label.setText("Ascent : " + str(ascent))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0503ab712e84bccbc1c9f70f7f144d28.png)