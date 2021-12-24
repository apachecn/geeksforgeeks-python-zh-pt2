# PyQt5 QSpinbox–如何从中拖动文本

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-如何从 it 中拖动文本/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-drag-text-from-it/)

在这篇文章中，我们将看到如何拖动文本/内容，即包括前缀和后缀的整个文本。当我们创建一个旋转框时，我们不能从中拖动文本，拖动文本意味着根据光标将选定的文本移动到任何位置。

为了做到这一点，我们对旋转框的线编辑对象使用了 setDragEnabled 方法。

> **语法:** line_edit.setDragEnabled(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # getting the line edit object
        line = self.spin.lineEdit()

        # enabling the drag 
        line.setDragEnabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411900-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200512232151/Python-12-05-2020-23_21_22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200512232151/Python-12-05-2020-23_21_22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200512232151/Python-12-05-2020-23_21_22.mp4)</video>