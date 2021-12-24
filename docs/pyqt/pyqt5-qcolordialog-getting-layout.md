# PyQt5 qcolor dialog–获取布局

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcolor dialog-get-layout/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-getting-layout/)

在本文中，我们将看到如何获得 QColorDialog 的布局。布局是存在于对话框中的所有子组件的映射，布局由对话框的子组件组成，每个小组件都是在布局中逐个添加的。

为了做到这一点，我们对 QColorDialog 对象使用`layout`方法

> **语法:**对话框.布局()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QLayout 对象

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

        # setting custom colors
        dialog.setCustomColor(1, Qt.red)
        dialog.setCustomColor(2, Qt.green)
        dialog.setCustomColor(3, Qt.yellow)
        dialog.setCustomColor(4, Qt.blue)

        # executing the dialog
        # dialog.exec_()

        # creating label
        label = QLabel("GeeksforGeeks", self)

        # setting geometry to the label
        label.setGeometry(10, 10, 400, 280)

        # making label multi line
        label.setWordWrap(True)

        # setting stylesheet of the label
        label.setStyleSheet("QLabel"
                            "{"
                            "border : 5px solid black;"
                            "}")

        # getting the custom color
        color = dialog.customColor(4)

        # setting graphic effect to the label
        graphic = QGraphicsColorizeEffect(self)

        # setting color to the graphic
        graphic.setColor(color)

        # setting graphic to the label
        label.setGraphicsEffect(graphic)

        # getting dialog layout
        value = dialog.layout()

        # setting text to the label
        label.setText("Layout : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/0aa2c84f704bdde341717f018b46e1a9.png)