# pyqt 5 qdatetimeedit–清算最大 QDateTime

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qdatetimeedit-clearing-maximum-qdatetime/

在本文中，我们将看到如何删除 QDateTimeEdit 小部件的最大 QDateTime。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以在`setDateTime`的帮助下设置日期时间。通过设置其最大值，确保用户不允许输入超过最大日期时间的日期时间，可以借助`setMaximumDateTime`方法进行设置。

为了做到这一点，我们将使用`clearMaximumDateTime`方法和 QDateTimeEdit 对象。

> **语法:**datetimeedit . clearmaximumatetime()
> 
> **论证:**不需要论证
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

        # creating a QDateTimeEdit widget
        datetimeedit = QDateTimeEdit(self)

        # setting geometry
        datetimeedit.setGeometry(100, 100, 150, 35)

        # date time
        dt = QDateTime(2020, 10, 10, 11, 30)

        # setting maximum date time to it
        datetimeedit.setMaximumDateTime(dt)

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 60)

        # making label multi line
        label.setWordWrap(True)

        # clearing maximum datetime
        datetimeedit.clearMaximumDateTime()

        # getting maximum date time
        value = datetimeedit.maximumDateTime()

        # setting text to the label
        label.setText("Max Date Time : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-451346-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200711024640/Python-2020-07-11-02-46-13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200711024640/Python-2020-07-11-02-46-13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200711024640/Python-2020-07-11-02-46-13.mp4)</video>