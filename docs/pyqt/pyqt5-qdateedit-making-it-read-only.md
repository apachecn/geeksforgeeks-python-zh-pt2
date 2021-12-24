# PyQt5 qdate edit–使其成为只读

> 原文:[https://www . geesforgeks . org/pyqt 5-qdatedit-making-it-只读/](https://www.geeksforgeeks.org/pyqt5-qdateedit-making-it-read-only/)

在本文中，我们将看到如何使日期编辑成为只读的。默认情况下，当我们创建日期编辑时，它是可编辑的，尽管我们可以将其设为只读。在只读模式下，用户仍然可以将文本复制到剪贴板，或者拖放文本，但不能编辑它。

为了做到这一点，我们对 QDateEdit 对象使用`setReadOnly`方法

> **语法:**日期. setReadOnly(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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
        date.setGeometry(100, 100, 200, 40)

        # alignment
        a_flag = Qt.AlignCenter

        # setting alignment of date
        date.setAlignment(a_flag)

        # making date edit read only
        date.setReadOnly(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-445993-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706001917/Python-2020-07-06-00-19-00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706001917/Python-2020-07-06-00-19-00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706001917/Python-2020-07-06-00-19-00.mp4)</video>