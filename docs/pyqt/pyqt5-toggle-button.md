# pyqt 5–切换按钮

> 原文:[https://www.geeksforgeeks.org/pyqt5-toggle-button/](https://www.geeksforgeeks.org/pyqt5-toggle-button/)

在 PyQt5 中，一个切换按钮基本上是处于特殊状态的按钮。按钮是一个按钮，当我们按下它时，它会执行一些任务并恢复到正常状态。它类似于键盘按键，当我们按下它时，它会执行一些操作，当我们释放它时，它会恢复到原来的状态。

**ToggleButton** 是按钮的一种，但是它有两种状态，即开和关，当我们按下它时，它不会回到原来的状态。拨动按钮类似于一个电开关，当我们按下它时，它保持打开状态，当我们关闭它时，它保持关闭状态。

> **为了创建切换按钮，我们必须执行以下操作:**
> 
> 1.  创建一个按钮。
> 2.  将“可检查”设置为“真”，也就是说，如果它被按下，它将被检查，如果它再次被按下，它将被取消选中，类似于复选框。
> 3.  设置按钮被按下时调用的调用方法。
> 4.  在调用方法时，检查按钮是否被选中。
> 5.  如果按钮被选中，改变它的颜色，否则设置它的默认颜色。

下面是实现。

```py
# importing the required libraries

from PyQt5.QtCore import * 
from PyQt5.QtGui import * 
from PyQt5.QtWidgets import * 
import sys

class Window(QMainWindow):
    def __init__(self):
        super().__init__()

        # set the title
        self.setWindowTitle("Python")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # creating a push button
        self.button = QPushButton("Toggle", self)

        # setting geometry of button
        self.button.setGeometry(200, 150, 100, 40)

        # setting checkable to true
        self.button.setCheckable(True)

        # setting calling method by button
        self.button.clicked.connect(self.changeColor)

        # setting default color of button to light-grey
        self.button.setStyleSheet("background-color : lightgrey")

        # show all the widgets
        self.update()
        self.show()

    # method called by button
    def changeColor(self):

        # if button is checked
        if self.button.isChecked():

            # setting background color to light-blue
            self.button.setStyleSheet("background-color : lightblue")

        # if it is unchecked
        else:

            # set background color back to light-grey
            self.button.setStyleSheet("background-color : lightgrey")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393245-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200331013649/Python-31-03-2020-01_35_28.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200331013649/Python-31-03-2020-01_35_28.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200331013649/Python-31-03-2020-01_35_28.mp4)</video>