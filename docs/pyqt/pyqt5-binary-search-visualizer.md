# PyQt5–二分搜索法可视化工具

> 原文:[https://www . geesforgeks . org/pyqt 5-binary-search-visualizer/](https://www.geeksforgeeks.org/pyqt5-binary-search-visualizer/)

在本文中，我们将看到如何制作一个 PyQt5 应用程序，它将可视化[二分搜索法](https://www.geeksforgeeks.org/binary-search/)算法。

**二分搜索法:**通过重复将搜索间隔减半来搜索排序后的数组。从覆盖整个数组的间隔开始。如果搜索关键字的值小于间隔中间的项目，请将间隔缩小到下半部分。否则缩小到上半部分。反复检查，直到找到值或间隔为空。
T3】

> **GUI 实现步骤:**
> 1。根据给定的数字列表
> 2 创建标签列表。将它们的文字、边框、颜色和几何图形设置为彼此有相应的间隙
> 3。每个标签高度应与每个数字
> 4 的值成比例。创建开始和暂停按钮，开始搜索并暂停搜索
> 5。创建结果标签以显示搜索状态
> 
> **算法实现步骤:**
> 1。创建对应于给定编号的标签列表
> 2。为第一个、最后一个和中间索引创建变量，并标记搜索。
> 3。向按钮添加动作，它们的动作应改变标志状态，即开始动作应使标志为真，暂停动作应使标志为假
> 4。创建定时器对象，该对象在每个特定时间后调用一个方法
> 5。在定时器方法内部检查标志是否为真，开始二分搜索法算法
> 6。计算中间值并检查中间值是否相等，然后停止搜索并使标签为绿色。
> 7。显示找到的结果，否则根据中间值更改第一次和最后一次搜索的值。将标签设为灰色并继续搜索。
> 8。如果第一个的索引变得大于最后一个的索引，则停止搜索并显示结果为未找到。

以下是实施–

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

class Window(QMainWindow):

    # list of numbers
    number = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,  13, 14, 15]

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Binary search ")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # start flag
        self.start = False

        # list to hold labels
        self.label_list = []

        # desired value
        self.desired = 9

        # binary search variable
        self.first = 0
        self.last = len(self.number) - 1
        self.mid = 0

        # local counter
        c = 0

        # iterating list of numbers
        for i in self.number:

            # creating label for each number
            label = QLabel(str(i), self)

            # adding background color and border
            label.setStyleSheet("border : 1px solid black; 
                                 background : white;")

            # aligning the text
            label.setAlignment(Qt.AlignTop)

            # setting geometry using local counter
            # first parameter is distance from left and 
            # second is distance from top
            # third is width and forth is height
            label.setGeometry(50 + c * 30, 50, 20, i * 10 + 10)

            # adding label to the label list
            self.label_list.append(label)

            # incrementing local counter
            c = c + 1

        # creating push button to start the search
        self.search_button = QPushButton("Start Search", self)

        # setting geometry of the button
        self.search_button.setGeometry(100, 270, 100, 30)

        # adding action to the search button
        self.search_button.clicked.connect(self.search_action)

        # creating push button to pause the search
        pause_button = QPushButton("Pause", self)

        # setting geometry of the button
        pause_button.setGeometry(100, 320, 100, 30)

        # adding action to the search button
        pause_button.clicked.connect(self.pause_action)

        # creating label to show the result
        self.result = QLabel("To search : " + str(self.desired), self)

        # setting geometry
        self.result.setGeometry(350, 280, 200, 40)

        # setting style sheet
        self.result.setStyleSheet("border : 3px solid black;")

        # adding font
        self.result.setFont(QFont('Times', 10))

        # setting alignment
        self.result.setAlignment(Qt.AlignCenter)

        # creating a timer object
        timer = QTimer(self)

        # adding action to timer
        timer.timeout.connect(self.showTime)

        # update the timer every 300 millisecond
        timer.start(300)

    # method called by timer
    def showTime(self):

        # checking if flag is true
        if self.start:
            # implementing binary search
            # finding mid index
            self.mid = (self.first + self.last)//2

            # if first index become greater than last index
            if self.first > self.last:

                # make start flag false
                self.start = False
                # show output as not found
                self.result.setText("Not Found")

            # if mid value is equal to the desired value
            if self.number[self.mid] == self.desired:

                # make flag false
                self.start = False

                # show output in result label
                self.result.setText("Found at index : " + str(self.mid))

                # set color of label to green
                self.label_list[self.mid].setStyleSheet(
                              "border : 2px solid green; "
                              "background-color : lightgreen")

            # if not equal to mid value
            else:
                # make color grey
                self.label_list[self.mid].setStyleSheet(
                                   "border : 1px solid black; "
                                   "background-color : grey")

            # mid value is higher
            if self.number[self.mid] > self.desired:
                # change last index
                self.last = self.mid - 1

            # if mid value is smaller
            if self.number[self.mid] < self.desired:
                # change first index
                self.first = self.mid + 1

    # method called by search button
    def search_action(self):

        # making flag true
        self.start = True

        # showing text in result label
        self.result.setText("Started searching...")

    # method called by pause button
    def pause_action(self):

        # making flag false
        self.start = False

        # showing text in result label
        self.result.setText("Paused")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-399526-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200420020005/Binary-search-20-04-2020-01_52_13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200420020005/Binary-search-20-04-2020-01_52_13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200420020005/Binary-search-20-04-2020-01_52_13.mp4)</video>