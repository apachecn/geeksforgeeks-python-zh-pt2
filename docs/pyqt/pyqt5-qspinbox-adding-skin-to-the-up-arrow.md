# PyQt5 QSpinBox–向上箭头

添加皮肤

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-向上箭头添加皮肤/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-skin-to-the-up-arrow/)

在本文中，我们将看到如何为旋转框的各种状态设置皮肤向上箭头。旋转框有两个子框，一个是行编辑，另一个是上下按钮。向上箭头是向上按钮的内部组件，基本上有三种状态，第一种是正常状态，第二种是悬停状态，即光标在向上箭头上时，第三种是按下状态。皮肤基本上是一个背景图像，可以根据旋转框的大小自行调整。

为了做到这一点，我们必须改变与旋转框相关的样式表，下面是样式表代码

```py
QSpinBox::up-arrow
{
border-image : url(image1.png);
}
QSpinBox::up-arrow:hover
{
border-image : url(image2.png);
}
QSpinBox::up-arrow:pressed
{
border-image : url(image3.png);
}

```

这将为向上箭头的每个状态添加三个不同的皮肤，还有一些额外的状态，如反悬停(！悬停)和反压(！按下)这分别与悬停和按下状态相反。

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
        # adding skin to spin box's up-arrow
        # adding skin to up arrow for hover and pressed state
        self.spin.setStyleSheet("QSpinBox::up-arrow"
                                "{"
                                "border-image : url(image.png);"
                                "}"
                                "QSpinBox::up-arrow:hover"
                                "{"
                                "border-image : url(skin.png);"
                                "}"
                                "QSpinBox::up-arrow:pressed"
                                "{"
                                "border-image : url(logo.png);"
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

<video class="wp-video-shortcode" id="video-421564-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200530025551/Python-2020-05-30-02-55-10.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200530025551/Python-2020-05-30-02-55-10.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200530025551/Python-2020-05-30-02-55-10.mp4)</video>