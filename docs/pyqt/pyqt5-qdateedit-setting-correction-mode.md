# pyqt 5 qdate edit–设置校正模式

> 原文:[https://www . geesforgeks . org/pyqt 5-qdate edit-setting-correction-mode/](https://www.geeksforgeeks.org/pyqt5-qdateedit-setting-correction-mode/)

在本文中，我们将了解如何将校正模式设置为 QDateEdit。在日期编辑中，更正非常重要，这样用户就不能输入无效日期。例如，如果用户试图输入大于 12 的月份值，当前值将返回到以前的有效值。下面给出了日期编辑的两种基本修正模式

`CorrectToPreviousValue`:日期编辑将恢复到最后一个有效值，其关联值为 0
`CorrectToNearestValue`:日期编辑将恢复到最近的有效值，其关联值为 1

为了做到这一点，我们对 QDateEdit 对象使用`setCorrectionMode`方法

> **语法:**date . setorrionmode(0)
> 
> **自变量:**以修正模式关联值为自变量
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

        # setting correction mode
        date.setCorrectionMode(0)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-444106-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200702025952/Python-2020-07-02-02-59-01.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200702025952/Python-2020-07-02-02-59-01.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200702025952/Python-2020-07-02-02-59-01.mp4)</video>