# PyQt5–鼠标悬停时将皮肤设置为未选中复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-皮肤-取消选中-鼠标悬停时复选框-2/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-unchecked-checkbox-when-mouse-hover-2/)

在本文中，我们将看到如何将皮肤设置为处于未选中状态的复选框的指示器，并将鼠标悬停在该指示器上。此外观仅在鼠标悬停在复选框上且其状态未选中时出现。

为了在复选框处于未选中状态并且鼠标悬停在指示器上时为指示器添加外观，我们必须更改样式表代码。下面是样式表代码。

```
QCheckBox::indicator:unchecked:hover
{
border-image : url(image.png);
}

```

下面是实现。

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
        # adding skin to unchecked indicator when mouse hover over it
        checkbox1.setStyleSheet("QCheckBox::indicator:unchecked:hover"
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

<video class="wp-video-shortcode" id="video-395477-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405003242/Python-05-04-2020-00_32_24.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405003242/Python-05-04-2020-00_32_24.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405003242/Python-05-04-2020-00_32_24.mp4)</video>