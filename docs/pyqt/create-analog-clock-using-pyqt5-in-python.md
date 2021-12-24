# 使用 Python 中的 PyQt5 创建模拟时钟

> 原文:[https://www . geesforgeks . org/create-analog-clock-use-pyqt 5-in-python/](https://www.geeksforgeeks.org/create-analog-clock-using-pyqt5-in-python/)

**先决条件:**[pyqt-5 简介](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/)

当一个时钟或手表有移动的指针和(通常)从数字 1 到 12 标记的小时来显示时间时，它被称为**“模拟”**。有的用罗马数字(I，II，III 等)代替，或者根本没有数字！换句话说:不是数字钟。

**PyQt5** 是一个跨平台的 GUI 工具包，一套针对 Qt v5 的 python 绑定。由于该库提供的工具和简单性，人们可以非常容易地开发交互式桌面应用程序。图形用户界面应用程序由前端和后端组成。

**进场:**

*   创建一个继承 QMainWindow 类的时钟类。
*   在时钟类中创建一个定时器对象，每秒钟更新整个代码。
*   为时钟的每个指针创建三个多边形对象。
*   创建绘制事件方法。
*   在 paint 事件方法中，获取当前时间和窗口宽度或高度的最小值。
*   创建一个画师对象和一个绘制手的方法。
*   在绘制指针的方法中，使用颜色、旋转和多边形对象等参数。
*   旋转油漆工对象并绘制指针。
*   在 paint 事件方法内部，根据当前时间设置旋转值并调用绘制指针方法。
*   绘制时钟的背景图像，即每小时的线条。

下面是实现:

## 蟒蛇 3

```
# importing libraries
from PyQt5.QtWidgets import *
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import *
from PyQt5.QtCore import *
import sys

# creating a clock class
class Clock(QMainWindow):

    # constructor
    def __init__(self):
        super().__init__()

        # creating a timer object
        timer = QTimer(self)

        # adding action to the timer
        # update the whole code
        timer.timeout.connect(self.update)

        # setting start time of timer i.e 1 second
        timer.start(1000)

        # setting window title
        self.setWindowTitle('Clock')

        # setting window geometry
        self.setGeometry(200, 200, 300, 300)

        # setting background color to the window
        self.setStyleSheet("background : black;")

        # creating hour hand
        self.hPointer = QtGui.QPolygon([QPoint(6, 7),
                                        QPoint(-6, 7),
                                        QPoint(0, -50)])

        # creating minute hand
        self.mPointer = QPolygon([QPoint(6, 7),
                                  QPoint(-6, 7),
                                  QPoint(0, -70)])

        # creating second hand
        self.sPointer = QPolygon([QPoint(1, 1),
                                  QPoint(-1, 1),
                                  QPoint(0, -90)])
        # colors
        # color for minute and hour hand
        self.bColor = Qt.green

        # color for second hand
        self.sColor = Qt.red

    # method for paint event
    def paintEvent(self, event):

        # getting minimum of width and height
        # so that clock remain square
        rec = min(self.width(), self.height())

        # getting current time
        tik = QTime.currentTime()

        # creating a painter object
        painter = QPainter(self)

        # method to draw the hands
        # argument : color rotation and which hand should be pointed
        def drawPointer(color, rotation, pointer):

            # setting brush
            painter.setBrush(QBrush(color))

            # saving painter
            painter.save()

            # rotating painter
            painter.rotate(rotation)

            # draw the polygon i.e hand
            painter.drawConvexPolygon(pointer)

            # restore the painter
            painter.restore()

        # tune up painter
        painter.setRenderHint(QPainter.Antialiasing)

        # translating the painter
        painter.translate(self.width() / 2, self.height() / 2)

        # scale the painter
        painter.scale(rec / 200, rec / 200)

        # set current pen as no pen
        painter.setPen(QtCore.Qt.NoPen)

        # draw each hand
        drawPointer(self.bColor, (30 * (tik.hour() + tik.minute() / 60)), self.hPointer)
        drawPointer(self.bColor, (6 * (tik.minute() + tik.second() / 60)), self.mPointer)
        drawPointer(self.sColor, (6 * tik.second()), self.sPointer)

        # drawing background
        painter.setPen(QPen(self.bColor))

        # for loop
        for i in range(0, 60):

            # drawing background lines
            if (i % 5) == 0:
                painter.drawLine(87, 0, 97, 0)

            # rotating the painter
            painter.rotate(6)

        # ending the painter
        painter.end()

# Driver code
if __name__ == '__main__':

  app = QApplication(sys.argv)

  # creating a clock object
  win = Clock()

  # show
  win.show()

  exit(app.exec_())
```

**输出:**

<video class="wp-video-shortcode" id="video-436714-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200622020605/Clock-2020-06-22-02-05-43.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200622020605/Clock-2020-06-22-02-05-43.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200622020605/Clock-2020-06-22-02-05-43.mp4)</video>