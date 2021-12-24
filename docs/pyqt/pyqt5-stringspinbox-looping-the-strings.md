# PyQt5 字符串文本框–循环字符串

> 原文:[https://www . geeksforgeeks . org/pyqt 5-stringspinbox-循环字符串/](https://www.geeksforgeeks.org/pyqt5-stringspinbox-looping-the-strings/)

在本文中，我们将看到如何让字符串值在最后一个值到达时重复它们自己，它应该回到第一个值。类似地，当值在第一个值之后递减时，它应该回到最后一个值。为此，我们必须更改 StringSpinBox 的自定义类代码。

下面是自定义 StringSpinBox 类的代码

```
# custom class for String Spin Box
class StringBox(QSpinBox):

    # constructor
    def __init__(self, parent=None):
        super(StringBox, self).__init__(parent)

        # list of strings
        strings = ["a", "b", "c", "d", "e", "f", "g"]

        # calling set Strings method with
        # adding blank value in front and in end
        self.setStrings(["BLANK"] + strings + ["BLANK"])

        # show first value from index 1
        self.setValue(1)

    def reset_spin(self):
        if self.value() == len(self.strings()) - 1:
            self.setValue(0)

    # method setString
    # similar to set value method
    def setStrings(self, strings):

        # making strings list
        strings = list(strings)

        # making tuple from the string list
        self._strings = tuple(strings)

        # creating a dictionary
        self._values = dict(zip(strings, range(len(strings))))

        # setting range to it the spin box
        self.setRange(0, len(strings)-1)

    # overwriting the textFromValue method
    def textFromValue(self, value):

        # returning string from index
        # _string = tuple
        return self._strings[value]

    # overwriting the stepBy method
    # method that get called when values get incremented or decremented
    def stepBy(self, step):

        # checking if current value is 1 and step is -1
        # step = -1 means decrement
        if self.value() == 1 and step == -1:

            # set current value to maximum
            self.setValue(self.maximum())

        # checking if current value is maximum -1 and step is 1
        # step = 1 means Increment
        elif self.value() == self.maximum() - 1 and step == 1:

            # setting current value to 0
            self.setValue(0)

        # calling stepBy method of QSpinBox
        QSpinBox.stepBy(self, step)

```

**解释:**在字符串旋转框中，自定义类覆盖当增量或减量发生时调用的 stepBy 方法，检查如果有减量并且当前值是最小值，则将其值更改为最大值类似地，如果有增量并且当前值是最大值，则将其值更改为最小值-1。

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# custom class for String Spin Box
class StringBox(QSpinBox):

    # constructor
    def __init__(self, parent = None):
        super(StringBox, self).__init__(parent)

        # list of strings
        strings = ["a", "b", "c", "d", "e", "f", "g"]

        # calling set Strings method with
        # adding blank value in front and in end
        self.setStrings(["BLANK"] + strings + ["BLANK"])

        # show first value from index 1
        self.setValue(1)

    def reset_spin(self):
        if self.value() == len(self.strings()) - 1:
            self.setValue(0)

    # method setString
    # similar to set value method
    def setStrings(self, strings):

        # making strings list
        strings = list(strings)

        # making tuple from the string list
        self._strings = tuple(strings)

        # creating a dictionary
        self._values = dict(zip(strings, range(len(strings))))

        # setting range to it the spin box
        self.setRange(0, len(strings)-1)

    # overwriting the textFromValue method
    def textFromValue(self, value):

        # returning string from index
        # _string = tuple
        return self._strings[value]

    # overwriting the stepBy method
    # method that get called when values incremented
    def stepBy(self, step):

        # checking if current value is 1 and step is -1
        # step = -1 means decrement
        if self.value() == 1 and step == -1:

            # set current value to maximum
            self.setValue(self.maximum())

        # checking if current value is maximum -1 and step is 1
        # step = 1 means Increment
        elif self.value() == self.maximum() - 1 and step == 1:

            # setting current value to 0
            self.setValue(0)

        # calling stepBy method by QSpinBox
        QSpinBox.stepBy(self, step)

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

        # creating a string spin box
        string_spin_box = StringBox(self)

        # setting geometry to the spin box
        string_spin_box.setGeometry(100, 100, 200, 40)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-413080-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515011113/Python-15-05-2020-01_04_13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515011113/Python-15-05-2020-01_04_13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515011113/Python-15-05-2020-01_04_13.mp4)</video>