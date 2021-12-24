# PyQt5–单选按钮的胶囊形指示器

> 原文:[https://www . geesforgeks . org/pyqt 5-胶囊形单选按钮指示器/](https://www.geeksforgeeks.org/pyqt5-capsule-shaped-indicator-of-radio-button/)

在这篇文章中，我们将看到如何制作胶囊形状的单选按钮指示器。默认情况下，单选按钮指示器是圆形的。
下图是普通单选按钮和指示器为胶囊形的单选按钮的图示。

![](img/bb9d7bf145a13348a7a0d1f77862a3bf.png) ![](img/ded3fafbdfcab0696ccf8463f048648d.png)

> **为了做到这一点我们必须做到以下几点:**
> 1。创建单选按钮。
> 2。在样式表的帮助下，设置边框并将单选按钮指示器做成矩形。
> 3。将边框半径更改为指示器高度和边框厚度的一半之和。

**执行此操作的样式表代码–**

```
QRadioButton::indicator
{
border : 1px solid black;
width : 25;
height : 12;
border-radius : 7;
}
```

下面是实现–

## 蟒蛇 3

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

        # changing style sheet code of radio button setting border to
        # indicator of thickness 1px and of black color and width and height
        # and the border radius equal to thickness of border + half of height
        self.radio_button.setStyleSheet("QRadioButton::indicator"
                                        "{"
                                        "border : 1px solid black;"
                                        "width : 25px;"
                                        "height : 12px;"
                                        "border-radius : 7px;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/0d6bc8a305942f6b6ea7814149ea09d3.png)