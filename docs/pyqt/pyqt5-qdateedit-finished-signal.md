# PYqt 5 QDateedit–完成信号

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-finished-signal/](https://www.geeksforgeeks.org/pyqt5-qdateedit-finished-signal/)

在本文中，我们将看到如何获得 QDateEdit 的最终信号。编辑完成后会发出此信号。当日期编辑失去焦点和按下回车键时，就会发生这种情况。这个信号非常重要，因为它只在编辑完成时发生，不像其他信号那样在很短的时间间隔内获得很多时间。

为了做到这一点，我们对 QDateEdit 对象使用`editingFinished`方法

> **语法:**日期.编辑完成.连接(方法)
> 
> **自变量:**以方法为自变量
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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QDateEdit widget
        date = QDateEdit(self)

        # setting geometry of the date edit
        date.setGeometry(100, 100, 150, 40)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry
        label.setGeometry(100, 150, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # getting finished signal
        date.editingFinished.connect(lambda: date_method())

        # method called by date edit
        def date_method():

            # setting text to the label
            label.setText("Finished Signal Emitted")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-444110-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200702031647/Python-2020-07-02-03-16-20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200702031647/Python-2020-07-02-03-16-20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200702031647/Python-2020-07-02-03-16-20.mp4)</video>