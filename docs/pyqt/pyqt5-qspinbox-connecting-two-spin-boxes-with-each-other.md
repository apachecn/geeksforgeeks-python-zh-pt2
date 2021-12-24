# PyQt5 QSpinBox–连接两个旋转盒

> 原文:[https://www . geesforgeks . org/pyqt5-qspinbox-connecting-two-spin-box-with-other-to-then/](https://www.geeksforgeeks.org/pyqt5-qspinbox-connecting-two-spin-boxes-with-each-other/)

在本文中，我们将了解如何将两个旋转框相互连接起来，以便一个旋转框中的每次值变化都应该反映在其他旋转框中，例如，当我们固定了图像的宽高比并允许用户使用旋转框设置宽度和高度时，由于该比是固定的，因此任何维度的变化也应该反映在其他维度中。

**示例:**
两个相互连接的旋转框，使得任何一个旋转框中的每一个值的变化都保持相等。

> 实施步骤:
> 
> 1.创建两个旋转框
> 2。向两个旋转框
> 3 添加几何图形。使用值更改信号
> 4 给每个旋转框添加动作。在第一个旋转框动作中获取旋转框的当前值，并将该值设置为第二个旋转框
> 5。在第二个旋转框操作中，获取旋转框的当前值，并将该值设置为第一个旋转框

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
        self.spin1 = QSpinBox(self)

        # setting geometry to spin box
        self.spin1.setGeometry(100, 100, 150, 40)

        # setting prefix to spin
        self.spin1.setPrefix("Width : ")

        # add action to this spin box
        self.spin1.valueChanged.connect(self.action_spin1)

        # creating another spin box
        self.spin2 = QSpinBox(self)

        # setting geometry to spin box
        self.spin2.setGeometry(300, 100, 150, 40)

        # setting prefix to spin box
        self.spin2.setPrefix("Height : ")

        # add action to this spin box
        self.spin2.valueChanged.connect(self.action_spin2)

    # method called after editing finished
    def action_spin1(self):

        # getting current value of spin box
        current = self.spin1.value()

        # setting this value to second spin box
        self.spin2.setValue(current)

        # method called after editing finished
    def action_spin2(self):
        # getting current value of spin box
        current = self.spin2.value()

        # setting this value to the first spin box
        self.spin1.setValue(current)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-413070-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200514201619/Python-14-05-2020-20_15_45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200514201619/Python-14-05-2020-20_15_45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200514201619/Python-14-05-2020-20_15_45.mp4)</video>