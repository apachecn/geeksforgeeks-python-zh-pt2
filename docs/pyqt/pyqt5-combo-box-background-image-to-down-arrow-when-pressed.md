# PyQt5 组合框–按下时背景图像向下箭头

> 原文:[https://www . geesforgeks . org/pyqt 5-组合框-背景-图像-向下箭头-按下时/](https://www.geeksforgeeks.org/pyqt5-combo-box-background-image-to-down-arrow-when-pressed/)

在本文中，我们将看到如何在组合框被按下时向其下箭头添加背景图像。向下箭头是组合框的组成部分，它充当用于显示列表视图的按钮。下拉箭头的背景图像只有在按下时才会出现。

为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码

```
QComboBox::down-arrow:pressed
{
background-image : url(image.png);
}

```

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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # making combo box editable
        self.combo_box.setEditable(True)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 200, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of combo box
        # adding background image to the down arrow when it get pressed
        self.combo_box.setStyleSheet("QComboBox::down-arrow:pressed"
                                     "{"
                                     "background-image : url(logo.png);"
                                     "border : 1px solid black;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-401657-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423004755/Python-23-04-2020-00_47_36.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423004755/Python-23-04-2020-00_47_36.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423004755/Python-23-04-2020-00_47_36.mp4)</video>