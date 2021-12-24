# PyQt5–鼠标悬停时将背景图像设置为组合框

> 原文:[https://www . geesforgeks . org/pyqt 5-设置-背景-图像到组合框-鼠标悬停时/](https://www.geeksforgeeks.org/pyqt5-setting-background-image-to-combobox-when-mouse-hover/)

在本文中，我们将看到当鼠标悬停在组合框上时，我们如何设置它的背景图像。默认情况下，组合框没有图像，尽管我们可以设置图像。只有当光标移动到组合框上时，背景图像才会出现

为了做到这一点，我们必须更改与组合框关联的样式表，下面是样式表代码–

```py
QComboBox::hover
{
background-image : url(image.png);
border :1px solid black;
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

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 200, 80)

        # making it editable
        # self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of the combo box
        # adding background image to the combo box when mouse hover
        self.combo_box.setStyleSheet("QComboBox::hover"
                                     "{"
                                     "background-image : url(image.png);"
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

<video class="wp-video-shortcode" id="video-400148-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200421013514/Python-21-04-2020-01_33_57.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200421013514/Python-21-04-2020-01_33_57.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200421013514/Python-21-04-2020-01_33_57.mp4)</video>