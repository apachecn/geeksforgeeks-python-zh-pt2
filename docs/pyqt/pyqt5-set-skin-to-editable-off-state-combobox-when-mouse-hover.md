# PyQt5–鼠标悬停时将皮肤设置为可编辑关闭状态组合框

> 原文:[https://www . geeksforgeeks . org/pyqt 5-设置-皮肤-可编辑-关闭-状态-鼠标悬停时组合框/](https://www.geeksforgeeks.org/pyqt5-set-skin-to-editable-off-state-combobox-when-mouse-hover/)

在本文中，我们将看到如何在可编辑组合框处于关闭状态时以及鼠标悬停在它上面时设置皮肤。皮肤基本上是背景图像，但皮肤根据组合框的大小调整其大小。关闭状态是当列表视图(项目视图)未打开时，使用`setEditable`方法使组合框可编辑。只有当组合框可编辑且处于打开状态且光标位于其上时，皮肤才会出现

为此，我们必须更改组合框的样式表代码，下面是样式表代码

```py
QComboBox::editable:!on:hover
{
border-image : url(image.png);
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

        # making combo box editable
        self.combo_box.setEditable(True)

        # geek list
        geek_list = ["Sayian", "Super Sayian", "Super Sayian 2", "Super Sayian B"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # setting style sheet of combo box
        # adding skin to the combo box when it is editable
        # and when it in off state and mouse hover over it
        self.combo_box.setStyleSheet("QComboBox::editable:! on:hover"
                                     "{"
                                     "border-image : url(image.png);"
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

<video class="wp-video-shortcode" id="video-402531-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200424023832/Python-24-04-2020-02_38_16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200424023832/Python-24-04-2020-02_38_16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200424023832/Python-24-04-2020-02_38_16.mp4)</video>