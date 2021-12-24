# PyQt5 QScrollBar–滑块按下信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qscrollbar-slider-pressed-signal/](https://www.geeksforgeeks.org/pyqt5-qscrollbar-slider-pressed-signal/)

在本文中，我们将看到如何获得 QScrollBar 的滑块按下信号。QScrollBar 是一个控件，它使用户能够访问比用于显示文档的小部件更大的文档部分。滑块是条内的可滚动对象。当用户用鼠标按下滑块时，或者当调用 setSliderDown(True)时，以编程方式发出此信号。

> 为此，我们将对滚动条对象使用 sliderPressed 方法。
> **语法:**scroll . sliderpreced . connect(方法)
> **参数:**以方法为参数
> **返回:**不返回

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        scroll = QScrollBar(self)

        # setting geometry of the scroll bar
        scroll.setGeometry(100, 50, 30, 200)

        # making its background color to green
        scroll.setStyleSheet("background : lightgrey;")

        # creating a label
        label = QLabel("GeesforGeeks", self)

        # setting geometry to the label
        label.setGeometry(200, 100, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # getting slider pressed signal
        scroll.sliderPressed.connect(lambda: do_action())

        # method called when signal is emitted
        def do_action():

            # setting text to the label
            label.setText("Slider Pressed Signal Emitted")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-460880-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200728012902/Python-2020-07-28-01-28-45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200728012902/Python-2020-07-28-01-28-45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200728012902/Python-2020-07-28-01-28-45.mp4)</video>