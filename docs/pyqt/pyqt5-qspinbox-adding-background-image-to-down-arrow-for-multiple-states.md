# PyQt5 QSpinBox–为多个状态的向下箭头添加背景图像

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-添加-背景-图像-向下箭头-适用于多种状态/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-background-image-to-down-arrow-for-multiple-states/)

在本文中，我们将看到如何为旋转框的各种状态设置背景图像。旋转框有两个子框，一个是行编辑，另一个是上下按钮。向上箭头是向上按钮的内部组件，向上箭头是显示的位置箭头，基本上有三种状态，第一种是正常状态，第二种是悬停状态，即光标在向下按钮上时，第三种是按下状态。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```py
QSpinBox::up-arrow
{
background-image : url(image1.png);
}
QSpinBox::up-arrow:hover
{
background-image : url(image2.png);
}
QSpinBox::up-arrow:pressed
{
background-image : url(image3.png);
}

```

这将为向上箭头的每个状态添加三个不同的背景图像，还有一些额外的状态，如反悬停(！悬停)和反压(！按下)这分别与悬停和按下状态相反。

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
        self.spin.setRange(0, 9999)

        # setting prefix to spin
        self.spin.setPrefix("PREFIX ")

        # setting suffix to spin
        self.spin.setSuffix(" SUFFIX")

        # setting style sheet
        # adding background image to up arrow
        # adding background image to up arrow
        # for hover and pressed state
        self.spin.setStyleSheet("QSpinBox::up-arrow"
                                "{"
                                "background-image : url(image.png);"
                                "}"
                                "QSpinBox::up-arrow:hover"
                                "{"
                                "background-image : url(skin.png);"
                                "}"
                                "QSpinBox::up-arrow:pressed"
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

<video class="wp-video-shortcode" id="video-420542-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200529003215/Python-2020-05-29-00-31-48.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200529003215/Python-2020-05-29-00-31-48.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200529003215/Python-2020-05-29-00-31-48.mp4)</video>