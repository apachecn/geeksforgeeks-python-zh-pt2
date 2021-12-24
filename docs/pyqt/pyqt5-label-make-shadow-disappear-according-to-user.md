# PyQt5 标签–根据用户

使阴影消失

> 原文:[https://www . geesforgeks . org/pyqt 5-标签-制作-阴影-消失-根据用户/](https://www.geeksforgeeks.org/pyqt5-label-make-shadow-disappear-according-to-user/)

在这篇文章中，我们将根据用户来看如何让标签的阴影消失。当用户选中单选按钮时，阴影将显示和消失，当单选按钮未选中时，阴影将出现。

> 为了做到这一点，我们使用`setEnabled`方法
> 
> **语法:**影子。setenv(bool)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**无

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

        # creating label
        label = QLabel("Label", self)

        # setting alignment
        label.setAlignment(Qt.AlignCenter)

        # setting geometry to the label
        label.setGeometry(200, 100, 150, 60)

        # setting border
        label.setStyleSheet("border : 8px solid black")

        # creating a QGraphicsDropShadowEffect object
        self.shadow = QGraphicsDropShadowEffect()

        # setting blur radius
        self.shadow.setBlurRadius(30)

        # setting Xoffset
        self.shadow.setOffset(10)

        # adding shadow to the label
        label.setGraphicsEffect(self.shadow)

        # creating radio button
        self.button = QRadioButton("Hide Shadow", self)

        # setting geometry to the radio button
        self.button.setGeometry(200, 200, 100, 40)

        # adding action to the button
        self.button.clicked.connect(self.hide_shadow)

    def hide_shadow(self):

        if self.button.isChecked():

            # making shadow off
            self.shadow.setEnabled(False)

        else:
            # making shadow off
            self.shadow.setEnabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-407358-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200503225447/Python-03-05-2020-22_53_51.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200503225447/Python-03-05-2020-22_53_51.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200503225447/Python-03-05-2020-22_53_51.mp4)</video>