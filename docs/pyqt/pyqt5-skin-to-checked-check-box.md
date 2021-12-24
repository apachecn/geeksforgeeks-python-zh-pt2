# pyqt 5–选中皮肤复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-待检查皮肤-复选框/](https://www.geeksforgeeks.org/pyqt5-skin-to-checked-check-box/)

在这篇文章中，我们将看到如何设置皮肤皮肤复选框时，它是在选中状态，默认情况下没有图像关联到复选框。皮肤基本上是一个根据复选框的大小自行调整的背景图像。

为了给选中状态复选框添加外观，我们必须更改样式表代码，下面是样式表代码。

```
QCheckBox::checked
{
border-image : url(image.png)
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

        # setting geometry of check box
        checkbox1.setGeometry(200, 150, 100, 40)

        # setting tri-state check box
        checkbox1.setTristate(True)

        # changing style sheet code of check box
        # adding skin to checked check box
        checkbox1.setStyleSheet("QCheckBox::checked"
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

<video class="wp-video-shortcode" id="video-394665-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404201247/Python-04-04-2020-20_09_08.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404201247/Python-04-04-2020-20_09_08.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404201247/Python-04-04-2020-20_09_08.mp4)</video>