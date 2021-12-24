# PyQt5 qcolor dialog–当前颜色变化信号

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcolor dialog-current-color-changed-signal/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-current-color-changed-signal/)

在本文中，我们将看到如何获得 QColorDialog 小部件的当前颜色变化信号。只要对话框中的当前颜色发生变化，就会发出此信号。当前颜色可以通过鼠标或键盘改变，也可以通过`setCurrentColor`方法编程改变

为了做到这一点，我们对 QColorDialog 对象使用`currentColorChanged`方法

> **语法:**dialog . currentcolorchanged . connect(lambda:print(" Color Changed "))
> 
> **自变量:**以方法为自变量
> 
> **执行的操作:**它调用传递的方法

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QColorDialog object
        dialog = QColorDialog(self)

        # getting color changed signal
        # when signal receives print the message
        dialog.currentColorChanged.connect(lambda: print("Color Changed"))

        # setting current color
        dialog.setCurrentColor(Qt.red)

        # executing the dialog
        dialog.exec_()

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 100, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting stylesheet of the label
        label.setStyleSheet("QLabel"
                            "{"
                            "border : 5px solid black;"
                            "}")

        color = Qt.darkBlue

        # setting graphic effect to the label
        graphic = QGraphicsColorizeEffect(self)

        # setting color to the graphic
        graphic.setColor(color)

        # setting graphic to the label
        label.setGraphicsEffect(graphic)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-436569-1" width="640" height="516" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200620004827/Select-Color-2020-06-20-00-47-53.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200620004827/Select-Color-2020-06-20-00-47-53.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200620004827/Select-Color-2020-06-20-00-47-53.mp4)</video>

```py
Color Changed
Color Changed
Color Changed
Color Changed

```