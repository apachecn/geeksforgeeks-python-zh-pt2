# PyQt5 QSpinBox–添加多状态背景图像

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-背景-多状态图像/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-image-for-multiple-states/)

在本文中，我们将看到如何为旋转框的各种状态设置背景图像。旋转框基本上有三种状态，一种是正常状态，第二种是悬停状态，即光标在旋转框上，第三种是按下状态，即按下鼠标按钮。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```
QSpinBox
{
border : 1px solid black;
background-image : url(image1.png);
}
QSpinBox::hover
{
background-image : url(image2.png);
}
QSpinBox::pressed
{
background-image : url(image3.png);
}

```

这将为每个状态添加三个不同的背景图像，还有一些额外的状态，如反悬停(！悬停)和反压(！按下)这分别与悬停和按下状态相反。

**注意:**我们必须为正常状态添加边框，否则图像不会显示，因为 PyQt5 不允许它覆盖样式表

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting range to the spin box
        self.spin.setRange(0, 9)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting style sheet
        # adding background image
        # adding background image for hover and pressed state
        self.spin.setStyleSheet("QSpinBox"
                                "{"
                                "border : 2px solid black;"
                                "background-image : url(image.png);"
                                "}"
                                "QSpinBox::hover"
                                "{"
                                "background-image : url(skin.png);"
                                "}"
                                "QSpinBox::pressed"
                                "{"
                                "background-image : url(logo.png);"
                                "}"
                                )

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-419760-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200528020843/Python-2020-05-28-02-08-16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200528020843/Python-2020-05-28-02-08-16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200528020843/Python-2020-05-28-02-08-16.mp4)</video>