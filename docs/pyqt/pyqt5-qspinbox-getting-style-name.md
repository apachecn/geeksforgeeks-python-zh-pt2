# PyQt5 QSpinBox–获取样式名称

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-get-style-name/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-style-name/)

在本文中，我们将看到如何获得旋转框文本的样式名。当开发人员创建了一个自定义样式并想为它命名以供自己使用时，使用样式名，这样样式名更容易理解。我们可以借助`setStyleName`方法将样式名称设置为旋转框的字体。

**注意:**字体匹配会忽略 style()和 weight()之类的属性，不过如果平台的字体引擎支持的话，可能会在之后进行模拟。

为了做到这一点，我们对旋转框的 QFont 对象使用`styleName`方法。

> **语法:** font.styleName()
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

        # setting style Name
        font.setStyleName("Geek")

        # reassigning this font to the spin box
        self.spin.setFont(font)

        # creating a label
        label = QLabel(self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 60)

        # getting style name
        style_name = font.styleName()

        # setting text to the label
        label.setText("Style Name : " + str(style_name))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/b738f1c2b4323ebec429907709fc1304.png)