# PyQt5 QCalendarWidget–如果可能的话访问每个孩子的矩形

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcalendarwidget-访问-每个孩子的矩形-如果可能/](https://www.geeksforgeeks.org/pyqt5-qcalendarwidget-accessing-rectangle-of-each-children-if-possible/)

在本文中，我们将看到如何获得 QCalendarWidget 所有子代的矩形。日历不是一个单独的小部件，它是许多小部件的混合物，我们称之为日历的孩子。有许多子视图，如表视图、项目委托等，我们使用 children 方法来获取它的所有子视图。矩形是每个子对象的边界矩形。
**注意:**所有的孩子都没有矩形，因为他们可以是一个布局。

> 为了做到这一点，我们必须做到以下几点:
> 1。创建日历小部件
> 2。获得所有孩子的日历
> 3。遍历孩子列表
> 4。尝试在尝试中获得矩形，除了阻止并将结果保存在另一个列表中
> 5。使用标签
> 显示列表

下面是实现

## 蟒蛇 3

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
        self.setGeometry(100, 100, 650, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QCalendarWidget object
        self.calendar = QCalendarWidget(self)

        # setting geometry to the calendar
        self.calendar.setGeometry(50, 10, 400, 250)

        # creating a label
        label = QLabel(self)

        # setting geometry
        label.setGeometry(50, 280, 420, 120)

        # making it multi line
        label.setWordWrap(True)

        # getting children
        children = self.calendar.children()

        value = []
        for i in children:
            try:

                try:
                    # getting children rectangle
                    rect = i.childrenRect()
                except:
                    # getting rectangle
                    rect = i.rect()

                # adding it to list
                value.append(rect)

            except:
                pass

        # setting text to the label
        label.setText("Rectangles : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/c3b09624c359065096511229204453b3.png)