# PyQt5–将皮肤设置为复选框

的未选中指示器

> 原文:[https://www . geesforgeks . org/pyqt 5-将皮肤设置为未选中-复选框指示器/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-unchecked-indicator-of-check-box/)

在本文中，我们将看到如何在复选框处于未选中状态时设置皮肤。默认情况下，未选中的指示器没有放置任何符号，尽管我们可以在图像中替换它。皮肤基本上是背景图像，可以根据复选框指示器的大小自行调整。

为了做到这一点，我们必须改变样式表代码，下面是样式表代码。

```
QCheckBox::indicator::unchecked
{
border-image : url(image.png)
}

```

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating the check-box
        checkbox1 = QCheckBox('Geek ?', self)

        # setting tristate check box
        checkbox1.setTristate(True)

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # changing style sheet code of check box
        # adding skin to unchecked indicator
        checkbox1.setStyleSheet("QCheckBox::indicator:unchecked"
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

<video class="wp-video-shortcode" id="video-395506-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405021300/Python-05-04-2020-02_12_37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405021300/Python-05-04-2020-02_12_37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405021300/Python-05-04-2020-02_12_37.mp4)</video>