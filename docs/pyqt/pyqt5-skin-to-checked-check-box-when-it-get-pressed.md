# PyQt5–按下皮肤复选框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-皮肤检查-按下时检查框/](https://www.geeksforgeeks.org/pyqt5-skin-to-checked-check-box-when-it-get-pressed/)

在这篇文章中，我们将看到如何设置皮肤复选框时，它已经处于选中状态，当它被按下，默认情况下没有皮肤关联到复选框，皮肤基本上是背景图像，可以根据复选框的大小自行调整。

为了在选中的复选框被按下时给它添加皮肤，我们必须编辑样式表代码，下面是样式表代码。

QCheckBox::选中::按下
{
边框-图像:URL(image . png)；

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

        # setting geometry
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating the check-box
        checkbox1 = QCheckBox('Geek ?', self)

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # changing style sheet code of check box
        # adding skin to checked check box when it get pressed
        checkbox1.setStyleSheet("QCheckBox::checked::pressed"
                                "{"
                                "border-image : url(image.png);"
                                "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-394663-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404012022/Python-04-04-2020-01_17_43.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404012022/Python-04-04-2020-01_17_43.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404012022/Python-04-04-2020-01_17_43.mp4)</video>