# pyqt 5–按下时将背景图像设置为不可编辑的组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-图像-不可编辑-组合框-按下时/](https://www.geeksforgeeks.org/pyqt5-set-background-image-to-non-editable-combobox-when-pressed/)

在本文中，我们将看到当组合框不可编辑并且被按下时，如何设置背景图像。默认情况下，组合框没有图像，尽管我们可以设置图像。只有当组合框处于不可编辑状态且组合框被按下时，背景图像才会出现。普通的组合框可以通过`setEditable`方法进行编辑。

为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码

```py
QComboBox::!editable:pressed
{
background-image : url(image.png);
border : 2px solid black;
}

```

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
        # creating a check-able combo box object
        self.combo_box = QComboBox(self)

        # making combo box editable
        # self.combo_box.setEditable(True)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 200, 80)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of the combo box
        # adding background image to the combo box it is in non-editable state
        # and when combo box get pressed

        self.combo_box.setStyleSheet("QComboBox::! editable:pressed"
                                     "{"
                                     "background-image : url(logo.png);"
                                     "border : 2px solid black;"
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

<video class="wp-video-shortcode" id="video-401694-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200422004632/Python-22-04-2020-00_44_13.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200422004632/Python-22-04-2020-00_44_13.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200422004632/Python-22-04-2020-00_44_13.mp4)</video>