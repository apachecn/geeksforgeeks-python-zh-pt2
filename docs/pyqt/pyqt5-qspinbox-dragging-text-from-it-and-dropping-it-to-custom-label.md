# PyQt5 QSpinbox–从中拖动文本并将其放到自定义标签

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-从其中拖放文本到自定义标签/](https://www.geeksforgeeks.org/pyqt5-qspinbox-dragging-text-from-it-and-dropping-it-to-custom-label/)

在本文中，我们将看到如何使用光标将旋转框的文本拖放到给定的自定义标签上。拖放文本类似于将一个文件夹从一个目录拖放到另一个目录，当我们这样做时，会生成它的另一个副本。

> 为此，我们必须执行以下操作:
> 
> 1.创建旋转框
> 2。获取旋转框
> 3 的线条编辑对象。对线编辑对象
> 4 启用拖动。为继承 QLabel 类
> 5 的自定义标签创建一个新类。允许本班接受滴滴
> 6。向它添加拖放事件，以便它可以接收文本并显示文本

**自定义标签类的语法**

```
class CustomLabel(QLabel):
    # constructor
    def __init__(self, title, parent):
        super().__init__(title, parent)

        # enabling accept drops
        self.setAcceptDrops(True)

    # creating drag enter event to receive text
    def dragEnterEvent(self, e):

        # checking format of the text
        if e.mimeData().hasFormat('text/plain'):
            # accepting the text
            e.accept()

        else:
            # rejecting the text
            e.ignore()

    # drop event to showing the text to label
    def dropEvent(self, e):

        # setting text to the label
        self.setText(e.mimeData().text())

```

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

        # get the line edit object
        line = self.spin.lineEdit()

        # set drag enable to true
        line.setDragEnabled(True)

        # creating a CustomLabel object
        label = CustomLabel('Drop here.', self)

        # setting geometry to the label
        label.setGeometry(100, 200, 300, 30)

class CustomLabel(QLabel):
    # constructor
    def __init__(self, title, parent):
        super().__init__(title, parent)

        # enabling accept drops
        self.setAcceptDrops(True)

    # creating drag enter event to receive text
    def dragEnterEvent(self, e):

        # checking format of the text
        if e.mimeData().hasFormat('text / plain'):
            # accepting the text
            e.accept()

        else:
            # rejecting the text
            e.ignore()

    # drop event to showing the text to label
    def dropEvent(self, e):

        # setting text to the label
        self.setText(e.mimeData().text())

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411861-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513002925/Python-13-05-2020-00_29_00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513002925/Python-13-05-2020-00_29_00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513002925/Python-13-05-2020-00_29_00.mp4)</video>