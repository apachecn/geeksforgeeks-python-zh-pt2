# pyqt 5 qdatetimeedit–qdatetime 已更改信号

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pyqt 5-qdatetimeedit-qdatetime-changed signal/

在本文中，我们将看到如何获取 QDateTimeEdit 小部件的 QDateTime 更改信号。QDateTime 基本上是 QDate 和 QTime 的组合，即它既有日期又有时间。而 QDateTimeEdit 小部件用于显示或接收 QDateTime。我们可以借助`setDateTime`方法将 QDateTime 设置为它。
当日期时间发生变化时，会发出该信号

为了做到这一点，我们将使用`dateTimeChanged`方法和 QDateTimeEdit 对象。

> **语法:**datetime edit . datetime changed . connect(方法)
> 
> **自变量:**以方法为自变量
> 
> **返回:**返回无

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * from PyQt5.QtCore import * import sys

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

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 160, 200, 60)

        # making label multi line
        label.setWordWrap(True)

        # datetime changed signal when emitted connect to the 
        # dt_method every time
        datetimeedit.dateTimeChanged.connect(lambda: dt_method())

        # method called by the datetime
        def dt_method():

            # getting current datetime
            value = datetimeedit.dateTime()

            # setting text to the label
            label.setText("New DateTime : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-449816-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200710022915/Python-2020-07-10-02-28-54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200710022915/Python-2020-07-10-02-28-54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200710022915/Python-2020-07-10-02-28-54.mp4)</video>