# PyQt5 qcolor dialog–所选颜色

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcolor dialog-selected-color/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-selected-color/)

在本文中，我们将看到如何获得 QColorDialog 小部件的选定颜色。选定颜色是用户通过单击“确定”或等效按钮选择的颜色。

**注意:**该颜色并不总是与 currentColor 属性所保持的颜色相同，因为用户可以在最终选择要使用的颜色之前选择不同的颜色。

为了做到这一点，我们对 QColorDialog 对象使用`selectedColor`方法

> **语法:**对话框.选择颜色()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QColor 对象

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QColorDialog object
        dialog = QColorDialog(self)

        # executing the dialog
        dialog.exec_()

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(100, 100, 300, 80)

        # making label multi line
        label.setWordWrap(True)

        # setting stylesheet of the label
        label.setStyleSheet("QLabel"
                            "{"
                            "border : 5px solid black;"
                            "}")

        # getting the selected color
        value = dialog.selectedColor()

        # setting text to the label
        label.setText("Selected Color : " + str(value))

        color = value

        # setting graphic effect to the label
        graphic = QGraphicsColorizeEffect(self)

        # setting color to the graphic
        graphic.setColor(color)

        # setting graphic to the label
        label.setGraphicsEffect(graphic)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-436571-1" width="640" height="516" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200620011255/Select-Color-2020-06-20-01-12-23.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200620011255/Select-Color-2020-06-20-01-12-23.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200620011255/Select-Color-2020-06-20-01-12-23.mp4)</video>

![](img/e787b945770cce071da21197474d7d32.png)