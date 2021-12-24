# pyqt 5–数字秒表

> 原文:[https://www.geeksforgeeks.org/pyqt5-digital-stopwatch/](https://www.geeksforgeeks.org/pyqt5-digital-stopwatch/)

在本文中，我们将看到如何使用 Python 图形用户界面——PyQt5 创建秒表。
秒表**是一款手持式时计，用于测量启动和停止之间的时间。设计用于远距离观看的秒表的大型数字版本，如在体育场中，被称为秒表。**

> ****创建秒表的步骤–****
> 
> **1.创建一个表示秒
> 2 的计数器。创建标志以知道何时开始和何时暂停，将其设置为假
> 3。创建显示秒的标签
> 4。创建三个按钮，用于启动秒表、暂停秒表和重新设置秒表
> 5。为每个按钮添加操作。
> 6。内部启动按钮动作使标志变为真
> 7。内部暂停按钮动作使标志变为假
> 8。内部复位按钮动作使标记为假，使计数器值为 0
> 9。创建每隔 100 毫秒调用一个方法的 QTimer 对象，即第二个
> 10 的第十部分。在 QTimer 对象方法中，检查标志状态，如果为真，递增计数器
> 11。使用 setText 方法通过标签显示计数器值。**

**以下是实施–**

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
        self.setWindowTitle("Python Stop watch")

        # setting geometry
        self.setGeometry(100, 100, 400, 500)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # counter
        self.count = 0

        # creating flag
        self.flag = False

        # creating a label to show the time
        self.label = QLabel(self)

        # setting geometry of label
        self.label.setGeometry(75, 100, 250, 70)

        # adding border to the label
        self.label.setStyleSheet("border : 4px solid black;")

        # setting text to the label
        self.label.setText(str(self.count))

        # setting font to the label
        self.label.setFont(QFont('Arial', 25))

        # setting alignment to the text of label
        self.label.setAlignment(Qt.AlignCenter)

        # creating start button
        start = QPushButton("Start", self)

        # setting geometry to the button
        start.setGeometry(125, 250, 150, 40)

        # add action to the method
        start.pressed.connect(self.Start)

        # creating pause button
        pause = QPushButton("Pause", self)

        # setting geometry to the button
        pause.setGeometry(125, 300, 150, 40)

        # add action to the method
        pause.pressed.connect(self.Pause)

        # creating reset button
        re_set = QPushButton("Re-set", self)

        # setting geometry to the button
        re_set.setGeometry(125, 350, 150, 40)

        # add action to the method
        re_set.pressed.connect(self.Re_set)

        # creating a timer object
        timer = QTimer(self)

        # adding action to timer
        timer.timeout.connect(self.showTime)

        # update the timer every tenth second
        timer.start(100)

    # method called by timer
    def showTime(self):

        # checking if flag is true
        if self.flag:

            # incrementing the counter
            self.count+= 1

        # getting text from count
        text = str(self.count / 10)

        # showing text
        self.label.setText(text)

    def Start(self):

        # making flag to true
        self.flag = True

    def Pause(self):

        # making flag to False
        self.flag = False

    def Re_set(self):

        # making flag to false
        self.flag = False

        # reseeting the count
        self.count = 0

        # setting text to label
        self.label.setText(str(self.count))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

****输出:**** 

**<video class="wp-video-shortcode" id="video-397291-1" width="640" height="800" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200412020635/Python-Stop-watch-12-04-2020-02_06_12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200412020635/Python-Stop-watch-12-04-2020-02_06_12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200412020635/Python-Stop-watch-12-04-2020-02_06_12.mp4)</video>**