# PyQt5–按下

时将皮肤设置为未选中单选按钮

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-皮肤-取消选中-单选按钮-按下时/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-unchecked-radio-button-when-pressed/)

在本文中，我们将看到当单选按钮被按下并且处于未选中状态时，如何设置皮肤。皮肤基本上是根据单选按钮的大小自行调整的背景图像。只有当单选按钮被按下并且已经处于未选中状态时，此外观才会出现。

为此，我们必须更改单选按钮的样式表代码，下面是样式表代码

```
QRadioButton::unchecked::pressed
{
border-image : url(image.png);
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
        # creating a radio button
        self.radio_button = QRadioButton(self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # setting text to radio button
        self.radio_button.setText("Radio Button")

        # changing style sheet code of radio button
        # setting skin for unchecked radio button when it get pressed
        self.radio_button.setStyleSheet("QRadioButton::unchecked:pressed"
                                        "{"
                                        "border-image: url(image.png);"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-395513-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200405234500/Python-05-04-2020-23_44_38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200405234500/Python-05-04-2020-23_44_38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200405234500/Python-05-04-2020-23_44_38.mp4)</video>