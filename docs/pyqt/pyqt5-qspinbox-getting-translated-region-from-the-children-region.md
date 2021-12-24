# PyQt5 QSpinBox–从子区域

获取翻译区域

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-get-translated-region-from-the-children-region/](https://www.geeksforgeeks.org/pyqt5-qspinbox-getting-translated-region-from-the-children-region/)

在本文中，我们将看到如何从旋转框的子区域中获取已翻译的区域，子区域保存旋转框的子区域所占据的组合区域。为了得到孩子区域，我们使用`childrenRegion`方法。平移区域表示沿 x 轴和 y 轴移动的子区域。

> 为此，我们对旋转框的子区域对象使用翻译方法
> 
> **语法:**children _ region . translated(x，y)
> 
> **自变量:**取两个整数作为自变量
> 
> **返回:**返回区域

**注意:**这个方法类似于`translate`方法，但是，这个方法不在子区域做改变。

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
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # getting the children region
        children_region = self.spin.childrenRegion()

        # creating a label
        label = QLabel(self)
        label.setWordWrap(True)

        # setting geometry to the label
        label.setGeometry(100, 200, 200, 60)

        # getting translated region from the children region
        translated_region = children_region.translated(100, 100)

        # setting text to the label
        label.setText("Translated region : " + str(translated_region.rects()))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
window.spin.setFocus()
# start the app
sys.exit(App.exec())
```

**输出:**
![](img/519d2212401689caf9707a3f37cebce1.png)