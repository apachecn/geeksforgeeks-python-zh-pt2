# PyQt5 QSpinbox–如何启用接受跌落

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-如何启用-接受-drops/](https://www.geeksforgeeks.org/pyqt5-qspinbox-how-to-enable-accept-drops/)

在这篇文章中，我们将看到如何在旋转框中启用接受拖放，我们知道我们可以使用`setDragEnabled`方法使用旋转框的线编辑对象来启用拖动，但是拖动我们不能放在任何地方的文本有什么用。允许接受拖放意味着旋转框现在有一个属性来接受拖放文本。

为了做到这一点，我们对旋转框使用`setAcceptDrops`方法。

> **语法:**line _ edit . setacceptdrops(true)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

**注意:这个方法只让 accept drop 属性为 true，以便接受和显示我们必须添加`dragEnterEvent`和`dropEvent`到旋转框对象的文本。**

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
        self.spin.setGeometry(100, 100, 250, 40)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # allowing accept drops
        self.spin.setAcceptDrops(True)

        # creating another spin box
        another_spin = QSpinBox(self)

        # setting drag enabled
        another_spin.lineEdit().setDragEnabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-411943-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513204312/Python-13-05-2020-20_37_47.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513204312/Python-13-05-2020-20_37_47.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513204312/Python-13-05-2020-20_37_47.mp4)</video>