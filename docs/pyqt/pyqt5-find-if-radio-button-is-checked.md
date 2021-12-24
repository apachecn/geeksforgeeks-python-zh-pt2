# PyQt5–查找单选按钮是否被选中

> 原文:[https://www . geesforgeks . org/pyqt5-如果单选按钮被选中，则查找/](https://www.geeksforgeeks.org/pyqt5-find-if-radio-button-is-checked/)

在本文中，我们将了解如何找到单选按钮是否被选中。默认情况下，单选按钮是未选中的，但是借助`setChecked`方法，我们可以将其设置为选中。

> **为了检查单选按钮是否被选中，我们将执行以下操作:**
> 
> 1.创建按钮
> 2。创建一个标签来告知单选按钮是否被选中。
> 3。将一个方法连接到它，这样如果它的状态改变了，就应该调用该方法。
> 4。在方法检查中，是否借助`isChecked`方法检查单选按钮。
> 5。根据状态更改标签的文本。

下面是实现。

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

        # creating a radio button
        self.radio_button = QRadioButton(self)

        # setting geometry of radio button
        self.radio_button.setGeometry(200, 150, 120, 40)

        # setting text to radio button
        self.radio_button.setText("GEEK ?")

        # creating label to display if it is checked or not
        self.label = QLabel("", self)

        # setting geometry of label
        self.label.setGeometry(200, 200, 150, 40)

        # setting callable method to radio button
        self.radio_button.clicked.connect(self.check)

    # method called by radio button
    def check(self):

        # checking if it is checked
        if self.radio_button.isChecked():

            # changing text of label
            self.label.setText("It is now checked")

        # if it is not checked
        else:

            # changing text of label
            self.label.setText("")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-393275-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200401001311/Python-01-04-2020-00_11_07.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200401001311/Python-01-04-2020-00_11_07.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200401001311/Python-01-04-2020-00_11_07.mp4)</video>