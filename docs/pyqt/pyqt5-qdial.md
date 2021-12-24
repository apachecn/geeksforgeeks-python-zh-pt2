# pyqt 5–qdial

> 哎哎哎::1230【https://www . geeksforgeeks . org/pyqt 5-qdial/

**QDial** 是 PyQt5 中的一个类，它为用户提供了在程序可定义的范围内选择值的功能，该范围可以是环绕的(例如，角度从 0 到 359 度测量)。同样，它也可以用来显示当前值，类似于速度计。下面是 QDial 的外观

![](img/507464ab4c1919c6f8da8b2f018aca58.png)

**示例:**
一个有 QDial 的窗口，用户可以更改它的值，当用户更改该值时，当前值将显示在标签中

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

        # creating QDial object
        dial = QDial(self)

        # setting geometry to the dial
        dial.setGeometry(100, 100, 100, 100)

        # adding action to the dial
        dial.valueChanged.connect(lambda: dial_method())

        # creating a label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(220, 125, 200, 60)

        # making label multiline
        label.setWordWrap(True)

        # method called by the dial
        def dial_method():

            # getting dial value
            value = dial.value()

            # setting text to the label
            label.setText("Current Value : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-446139-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706005301/Python-2020-07-06-00-52-28.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706005301/Python-2020-07-06-00-52-28.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706005301/Python-2020-07-06-00-52-28.mp4)</video>