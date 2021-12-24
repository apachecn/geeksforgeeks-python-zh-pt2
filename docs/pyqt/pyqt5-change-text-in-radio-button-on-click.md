# PyQt5–点击

更改单选按钮中的文本

> 原文:[https://www . geesforgeks . org/pyqt 5-更改-单选按钮中的文本-单击/](https://www.geeksforgeeks.org/pyqt5-change-text-in-radio-button-on-click/)

在本文中，我们将看到如何更改单选按钮中的文本。当我们创建单选按钮时，我们会设置一些文本，甚至可以将其留空，单选按钮是在`QRadioButton`类的帮助下创建的。

我们将创建一个单选按钮和一个按钮，这样当按下按钮时，单选按钮文本将会改变。

> **为此，我们必须执行以下操作–**
> 
> *   创建单选按钮。
> *   创建一个按钮。
> *   连接一个与按钮相关联的方法，这样当按钮被按下时，这个方法就会被调用。
> *   在方法中，借助`setText`方法更改单选按钮内容。

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
        self.button1 = QRadioButton("Button1", self)

        # setting geometry of radio button
        self.button1.setGeometry(200, 150, 100, 40)

        # creating push button
        self.push = QPushButton("Change the text ", self)

        # setting geometry of push button
        self.push.setGeometry(200, 200, 100, 40)

        # connect push button to method
        self.push.clicked.connect(self.changeName)

    # creating changeName method
    def changeName(self):

        # setting new text to radio button
        self.button1.setText("New Name")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393241-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200331161422/Python-31-03-2020-16_13_44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200331161422/Python-31-03-2020-16_13_44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200331161422/Python-31-03-2020-16_13_44.mp4)</video>