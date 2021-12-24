# PyQt5–鼠标悬停在可编辑组合框上时为其添加边框

> 原文:[https://www . geesforgeks . org/pyqt 5-将边框添加到可编辑组合框-当鼠标悬停在其上时/](https://www.geeksforgeeks.org/pyqt5-adding-border-to-editable-combo-box-when-mouse-hover-over-it/)

在本文中，我们将看到当组合框是可编辑的并且鼠标悬停在它上面时，如何向它添加边框。默认情况下，组合框有边框虽然我们可以更改边框，但带有自定义边框的组合框只有在可编辑且光标位于其上时才会出现。借助`setEditable`方法可以制作可编辑的组合框

为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码

```py
QComboBox::editable:hover
{
border : 3px solid blue;
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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 150, 30)

        # making combo box editable
        self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # editing style sheet code of combo box
        # adding border to the combo box when it is editable
        # and when mouse hover over it
        self.combo_box.setStyleSheet("QComboBox::editable:hover"
                                     "{"
                                     "border : 3px solid blue;"
                                     "}")

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-399929-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200418192418/Python-18-04-2020-19_23_27.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200418192418/Python-18-04-2020-19_23_27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200418192418/Python-18-04-2020-19_23_27.mp4)</video>