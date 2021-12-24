# PyQt5 QSpinBox–进行更新

> 原文:[https://www . geesforgeks . org/pyqt 5-qspinbox-making-updates/](https://www.geeksforgeeks.org/pyqt5-qspinbox-making-updates/)

在本文中，我们将了解如何在发生任何更改时更新旋转框，在传统的图形用户界面构建中，每次我们对小部件进行更改时，我们都必须更新小部件，以便用户可以看到新更新的旋转框。例如，在 PyGame 中，当我们进行更改时，我们必须刷新屏幕或更新屏幕，以便显示新事件。但是在 PyQt5 中，每次发生变化时，自旋盒都会自动更新自己，尽管我们可以调用`update`方法来显式更新它。

**注意:**除非旋转框更新被禁用或隐藏

为了做到这一点，我们使用`update`方法。

> **语法:**旋转框.更新()
> 
> **论证:**不需要论证
> 
> **执行的动作:**更新旋转框

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
        # creating spin box
        self.spin = QSpinBox(self)

        # setting geometry to spin box
        self.spin.setGeometry(100, 100, 250, 40)

        # setting prefix to spin
        self.spin.setPrefix("Prefix ")

        # setting suffix to spin
        self.spin.setSuffix(" Suffix")

        # making updates on spin box
        self.spin.update()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-410714-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200511022448/Python-11-05-2020-02_24_21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200511022448/Python-11-05-2020-02_24_21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200511022448/Python-11-05-2020-02_24_21.mp4)</video>