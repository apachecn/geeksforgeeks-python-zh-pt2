# pyqt 5–进度条的多色边框

> 原文:[https://www . geesforgeks . org/pyqt 5-多色边框到进度条/](https://www.geeksforgeeks.org/pyqt5-multi-colored-border-to-bar-of-progress-bar/)

在本文中，我们将看到如何创建进度条的多色边框。进度条是进度条的一部分，表示完成情况。

下面是进度条边框条与进度条多色条的图示。

![](img/d27ca6c869285ba3c5f6dbf8c39be1c6.png) ![](img/c433dd8512bc35c0f314f93c8c8f782e.png)
为了这个我们在 CSS 样式表中改变了进度条每个边框的颜色，下面是边框样式表的代码。

```py
QProgressBar
{
border : 1px solid black;
}
QProgressBar::chunk
{
border :3px solid ;
border-top-color : red; 
border-left-color :pink;
border-right-color :green;
border-bottom-color : blue;
}

```

下面是实现。

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

        # setting background color to window
        # self.setStyleSheet("background-color : yellow")

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):
        # creating progress bar
        bar = QProgressBar(self)

        # setting geometry to progress bar
        bar.setGeometry(200, 100, 200, 30)

        # setting the value
        value = 70
        bar.setValue(value)

        # setting alignment to center
        bar.setAlignment(Qt.AlignCenter)

        # setting border to progress bar
        # and setting multi colored border to the bar and color
        bar.setStyleSheet("QProgressBar "
                          "{"
                          "border : 1px solid black;"
                          "}"
                          "QProgressBar::chunk"
                          "{"
                          "background-color : yellow;"
                          "border :3px solid;"
                          "border-top-color : red;" 
                          "border-left-color :pink;"
                          "border-right-color :green;"
                          "border-bottom-color : blue;"
                          "}"
                          )

App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e2c572f099b409a0427c562140b1467e.png)