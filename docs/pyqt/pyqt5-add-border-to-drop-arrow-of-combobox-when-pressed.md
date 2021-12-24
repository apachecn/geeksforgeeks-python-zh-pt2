# PyQt5–按下时向组合框的下拉箭头添加边框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-添加边框到下拉箭头-组合框-按下时/](https://www.geeksforgeeks.org/pyqt5-add-border-to-drop-arrow-of-combobox-when-pressed/)

在这篇文章中，我们将看到当组合框的下拉箭头被按下时，我们如何与它接壤。下拉箭头基本上是一个按钮，按下时会打开列表视图。这个自定义边框只有在下拉箭头被按下时才会出现。
为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码

```
QComboBox::drop-arrow:pressed
{
border : 2px solid green;
}
```

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet code of combo box
        # adding border to the drop arrow when it get pressed
        self.combo_box.setStyleSheet("QComboBox::down-arrow:pressed"
                                     "{"
                                     "border : 2px solid green;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-399994-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200419233901/Python-19-04-2020-23_30_17.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200419233901/Python-19-04-2020-23_30_17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200419233901/Python-19-04-2020-23_30_17.mp4)</video>