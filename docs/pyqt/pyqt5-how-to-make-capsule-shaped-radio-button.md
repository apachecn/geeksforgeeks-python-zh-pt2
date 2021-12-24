# pyqt 5–如何制作胶囊形状的单选按钮？

> 原文:[https://www . geesforgeks . org/pyqt 5-如何制作胶囊形单选按钮/](https://www.geeksforgeeks.org/pyqt5-how-to-make-capsule-shaped-radio-button/)

在本文中，我们将看到如何创建胶囊形状的单选按钮。默认情况下，单选按钮的形状是矩形，胶囊形状基本上是矩形两端有两个半圆的形状。

下面是普通边框单选按钮和胶囊形单选按钮的图示。
![](img/51597a5c88fd2c6f222c9b1c7e77611b.png) ![](img/de72b9876eede2a8e3a38b827c3c24e8.png)

> **为了做到这一点，我们必须做到以下几点:**
> 
> 1.创建单选按钮
> 2。设置宽度大于单选按钮
> 3 的高度。添加边框
> 4。将单选按钮的半径设置为高度的一半

**向单选按钮添加边框和半径的样式表代码–**

```py
QRadioButton
{
border : 3px solid black;
border-radius : 20px;
}

```

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

        # creating a radio button
        self.radio_button = QRadioButton(self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # setting text to radio button
        self.radio_button.setText("Radio Button")

        # changing style sheet code of radio button setting border to
        # radio button and changing radius to half of height
        self.radio_button.setStyleSheet("QRadioButton"
                                        "{"
                                        "border : 3px solid black;"
                                        "border-radius : 20px;"
                                        "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/4988d1f310f40928853c0d54b10e6e5e.png)