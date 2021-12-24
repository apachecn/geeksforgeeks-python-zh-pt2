# PyQt5–如何制作圆形单选按钮？

> 原文:[https://www . geesforgeks . org/pyqt 5-如何制作圆形单选按钮/](https://www.geeksforgeeks.org/pyqt5-how-to-make-round-radio-button/)

在本文中，我们将看到如何创建圆形单选按钮。默认情况下，单选按钮的形状是矩形的，尽管如果我们设置宽度等于高度，它会变成正方形。下面是普通边框单选按钮与圆形单选按钮的图示。
![](img/881b87fc4d4d4b1b265ecc45b2cd6166.png) ![](img/0b5518869372ad267c3ccb960b9b5e52.png)

> **为了做到这一点，我们必须做到以下几点:**
> 
> 1.创建单选按钮。
> 2。将其宽度设置为与高度相等，使其呈方形
> 3。借助`setStyleSheet`方法为其添加边框。
> 4。将边框半径设置为宽度的一半。

**执行此操作的样式表代码–**

```py
QRadioButton
{
border : 3px solid black;
border-radius : 60px;
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

        # creating a radio button
        self.radio_button = QRadioButton(self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 120)

        # setting text to radio button
        self.radio_button.setText("Radio Button")

        # changing style sheet code of radio button setting border to
        # radio button and changing radius to half of width
        self.radio_button.setStyleSheet("QRadioButton"
                                        "{"
                                        "border : 3px solid black;"
                                        "border-radius : 60px;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8cdfb6f2e84c44b5c4132319af6ce756.png)