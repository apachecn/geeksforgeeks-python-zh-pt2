# pyqt 5–将蒙皮设置为不确定复选框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-将皮肤设置为不确定复选框/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-indeterminate-check-box/)

在这篇文章中，我们将看到我们如何设置皮肤复选框时，它处于不确定(中间)状态，皮肤，即图像只出现在复选框进入不确定状态。皮肤基本上是一个背景图像，它会根据复选框的大小自行调整。

不确定(中间)状态是复选框的第三种状态，介于选中和未选中状态之间，可以借助`setTristate`方法创建。

为了给不确定复选框添加皮肤，我们必须更改样式表代码，下面是样式表代码。

```py
QCheckBox::indeterminate
{
border-image : url(image.png);
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
        # adding skin to indeterminate check box
        checkbox1.setStyleSheet("QCheckBox::indeterminate"
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

<video class="wp-video-shortcode" id="video-395465-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200404203706/Python-04-04-2020-20_35_47.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200404203706/Python-04-04-2020-20_35_47.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200404203706/Python-04-04-2020-20_35_47.mp4)</video>