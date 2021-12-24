# PyQt5 QSpinBox–添加循环

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qspinbox-添加-循环/](https://www.geeksforgeeks.org/pyqt5-qspinbox-adding-looping/)

在本文中，我们将看到如何向旋转框添加循环，当我们默认创建一个旋转框时，当它达到最大值时，它不能再增加，同样，当它达到最小值时，它不能再减少。通过将循环添加到旋转框中，这些值在达到最大值或最小值后自行重复。

> 实施步骤:
> 
> 1.创建窗口
> 2。创建旋转框
> 3。设置旋转框的范围，使其具有一个额外的最小值和最大值，例如，如果我们想要从 0 到 100 的值，请将范围设置为-1 到 101
> 4。将动作添加到旋转框中，这样每次它的值改变时，动作应该被称为
> 5。在动作内部获取旋转框的当前值。
> 6。检查当前值是否等于最小值，然后将旋转框的当前值设置为最大值–1
> 7。否则检查当前值是否等于最大值，然后将旋转框的当前值设为最小值+ 1

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
        self.spin.setGeometry(100, 100, 150, 40)

        # setting range to the spin box
        self.spin.setRange(-1, 11)

        # setting prefix to spin
        self.spin.setPrefix("Value : ")

        # add action to this spin box
        self.spin.valueChanged.connect(self.action_spin)

    # method called after editing finished
    def action_spin(self):

        # getting current value of spin box
        current = self.spin.value()

        # checking if current value is minimum
        if current == -1:

            # setting spin box value to maximum - 1
            self.spin.setValue(10)

        # checking if current value is maximum
        elif current == 11:

            # setting spin box value to minimum + 1
            self.spin.setValue(0)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-413076-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515001220/Python-15-05-2020-00_09_53.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515001220/Python-15-05-2020-00_09_53.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515001220/Python-15-05-2020-00_09_53.mp4)</video>