# PyQt5–设置背景图像以查看组合框的一部分

> 原文:[https://www . geesforgeks . org/pyqt 5-set-background-image-to-view-part-of-combobox/](https://www.geeksforgeeks.org/pyqt5-set-background-image-to-view-part-of-combobox/)

在本文中，我们将看到如何将背景图像设置为组合框的视图部分，组合框的视图部分是显示所有项目的下拉菜单。为了向组合框添加或检索视图对象，我们使用`setView`和`view`方法。下面是查看零件的背景图像的外观

![](img/a0606d4580ec06c59091a2b81446b80a.png)

为了做到这一点，我们必须改变与之相关的样式表代码，下面是样式表代码

```
QListView
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

        # setting style sheet of the combo box
        # adding background image to the view part of combo box
        print(type(self.combo_box.view()))
        self.combo_box.setStyleSheet("QListView"
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
![](img/1ac555a1b3c04f3af582ea9ac92679f6.png)