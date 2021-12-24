# PyQt5–创建弦旋转盒

> 原文:[https://www . geesforgeks . org/pyqt5-creating-string-spin-box/](https://www.geeksforgeeks.org/pyqt5-creating-string-spin-box/)

在本文中，我们将看到如何创建一个有字符串值的旋转框，默认情况下旋转框只包含整数值。字符串旋转框是一个旋转框，它具有从给定字符串值中选择的字符串值。

为了创建一个字符串旋转框，我们创建了一个继承了 QSpinBox 类的自定义类，下面是字符串旋转框类语法

```py
# custom class for String Spin Box
class StringBox(QSpinBox):

    # constructor
    def __init__(self, parent=None):
        super(StringBox, self).__init__(parent)

        # string values
        strings = ["a", "b", "c", "d", "e", "f", "g"]

        # calling setStrings method
        self.setStrings(strings)

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

```

**解释:**这个类的基本思想是我们创建一个自定义类，它继承了自旋盒类，这就是为什么它具有普通自旋盒的所有能力，但是它没有显示整数，而是显示字符串值。我们已经创建了字典，这样对于每个字符串，它都有一个整数键，数字显示框的范围是字符串值的数量，并且在覆盖 textFromValue 方法的帮助下，它显示字符串而不是整数。

下面是实现

```py
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

        # string values
        strings = ["a", "b", "c", "d", "e", "f", "g"]

        # calling setStrings method
        self.setStrings(strings)

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

<video class="wp-video-shortcode" id="video-413078-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515004150/Python-15-05-2020-00_41_14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515004150/Python-15-05-2020-00_41_14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515004150/Python-15-05-2020-00_41_14.mp4)</video>