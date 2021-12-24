# PyQt5–获取按钮的大小

> 原文:[https://www . geesforgeks . org/pyqt5-获取按钮大小/](https://www.geeksforgeeks.org/pyqt5-get-the-size-of-push-button/)

在本文中，我们将看到如何获得按钮的大小。基本上有两种方法可以得到按钮的大小。让我们用例子来看看他们两个。

**方法 1:** **使用`size`方法。**

该方法将返回`QSize object`，它将告诉按钮的宽度和高度。

> **语法:** button.size()
> 
> **论证:**不需要论证。
> 
> **返回:**返回 QSize 对象。

**代码:**

```
# importing libraries
from PyQt5.QtWidgets import * 
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

    # method for widgets
    def UiComponents(self):

        # creating a push button
        button = QPushButton("CLICK", self)

        # setting geometry of button
        # rectangular shape i.e width > height
        button.setGeometry(200, 150, 150, 40)

        # adding action to a button
        button.clicked.connect(self.clickme)

        # printing button size
        print(button.size())

    # action method
    def clickme(self):

        # printing pressed
        print("pressed")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
```

**输出:**

```
PyQt5.QtCore.QSize(150, 40)
```

**方法二:**使用`geometry`或`rect`方法。

这些方法将返回`QRect object`，它将告诉按钮的宽度和高度以及按钮的位置。

> **语法:**
> 
> ```
> button.geometry()
> button.rect()
> 
> ```
> 
> **论证:**两者都不需要论证。
> 
> **返回:**两者都返回 QRect 对象。

**代码:**

```
# importing libraries
from PyQt5.QtWidgets import * 
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

    # method for widgets
    def UiComponents(self):

        # creating a push button
        button = QPushButton("CLICK", self)

        # setting geometry of button
        # rectangular shape i.e width > height
        button.setGeometry(200, 150, 150, 40)

        # adding action to a button
        button.clicked.connect(self.clickme)

        # printing button size
        print(button.geometry())
        print(button.rect())

    # action method
    def clickme(self):

        # printing pressed
        print("pressed")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()
```

**输出:**

```
PyQt5.QtCore.QRect(200, 150, 150, 40)
PyQt5.QtCore.QRect(0, 0, 150, 40)

```

**注:**`geometry`和`rect`方法给出的尺寸结果相同，但位置不同。`geometry`将给出主窗口的位置，`rect`方法将给出自身的位置。