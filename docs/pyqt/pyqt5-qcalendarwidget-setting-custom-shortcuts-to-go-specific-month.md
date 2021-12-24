# PyQt5 QCalendarWidget–设置自定义快捷方式前往特定月份

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-设置-自定义-快捷方式-前往特定月份/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-setting-custom-shortcuts-to-go-specific-month/)

在本文中，我们将了解如何为 QCalendarWidget 设置自定义快捷方式，以进入特定月份，例如，当用户按下“0”键时，日历也应该为其他月份显示类似的十月。对于像一月、六月和七月这样有相同首字母的月份，当按下“J”键时，它应该是下个月到当前月份，例如，如果当前月份是六月，按下“J”键，它应该显示七月，如果当前月份是七月，它应该显示一月。

> 实施步骤:
> 1。创建主窗口
> 2。创建一个 QCalendarWidget
> 3。将各种属性设置到日历
> 4。抓住日历的键盘，使默认的键盘功能不能发生
> 5。覆盖按键事件
> 6。在覆盖方法中，创建所有月份的键列表
> 7。获取日历的当前月份和年份
> 8。检查是否按下了“J”键，然后检查当月是否为 1 月，然后将当月设置为 6 月，如果当月为 6 月，则将当月设置为 7 月，否则将当月设置为 1 月
> 9。检查是否按下“M”键，然后检查当月是否为 3 月，然后将当月设置为 5 月，否则将当月设置为 3 月
> 10 同样，检查是否按下“A”键，然后检查当月是否为 4 月，将当月设置为 8 月，否则将当月设置为 4 月
> 11。如果按下任何其他键，检查该键是否出现在月份列表中，然后获取该键在列表中的索引，然后将当前月份设置为索引+ 1

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calender
        self.calendar.setGeometry(50, 10, 400, 250)

        # setting cursor
        self.calendar.setCursor(Qt.PointingHandCursor)

        # grabbing the keyboard for the calendar
        # to stop the predefined action
        self.calendar.grabKeyboard()

    # overriding key release event
    def keyPressEvent(self, e):

        # creating a key list according to the month
        keylist = [Qt.Key_J, Qt.Key_F, Qt.Key_M, Qt.Key_A, Qt.Key_M, Qt.Key_J,
                   Qt.Key_J, Qt.Key_A, Qt.Key_S, Qt.Key_O, Qt.Key_N, Qt.Key_D]

        # getting current month
        month = self.calendar.monthShown()

        # getting current year
        year = self.calendar.yearShown()

        # when J key is pressed
        if e.key() == keylist[0]:
            print("J Key Pressed")

            # if current month is January
            if month == 1:

                # set month as June
                self.calendar.setCurrentPage(year, 6)

            # if current month is June
            elif month == 6:

                # set month as July
                self.calendar.setCurrentPage(year, 7)

            # if current month is not june or july
            else:

                # set month as January
                self.calendar.setCurrentPage(year, 1)

        # if M key is pressed
        elif e.key() == keylist[2]:
            print("M key pressed")

            # if current month is March
            if month == 3:

                # set month as May
                self.calendar.setCurrentPage(year, 5)

            # if current month is not May
            else:
                # set month as March
                self.calendar.setCurrentPage(year, 3)

        # if A key is pressed
        elif e.key() == keylist[3]:
            print("A key pressed")

            # if current month is April
            if month == 4:

                # set month as August
                self.calendar.setCurrentPage(year, 8)

            # if current month is not August
            else:
                # set month as April
                self.calendar.setCurrentPage(year, 4)

        # if any other key is pressed
        elif e.key() in keylist:

            # get the position of the key in the list
            index = keylist.index(e.key())
            print(str(index + 1) + " Month Key Pressed")

            # set the month
            self.calendar.setCurrentPage(year, index + 1 )

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

<video class="wp-video-shortcode" id="video-429426-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200611020832/Python-2020-06-11-02-08-02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200611020832/Python-2020-06-11-02-08-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200611020832/Python-2020-06-11-02-08-02.mp4)</video>
**Output :**

```py
A key pressed
A key pressed
J Key Pressed
J Key Pressed
J Key Pressed
10 Month Key Pressed
12 Month Key Pressed
2 Month Key Pressed
11 Month Key Pressed
J Key Pressed
A key pressed
J Key Pressed
A key pressed
J Key Pressed
10 Month Key Pressed

```