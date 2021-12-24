# PyQt5 qcolor dialog–获取当前颜色

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcolor dialog-get-current-color/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-getting-current-color/)

在本文中，我们将看到如何获得 QColorDialog 小部件的当前颜色。用户可以用鼠标或使用旋转框选择颜色，但初始颜色始终保持白色。为了改变这一点，我们可以在执行之前设置颜色对话框的当前颜色。借助`setCurrentColor`方法选择当前颜色。

为了做到这一点，我们对 QColorDialog 对象使用`currentColor`方法

> **语法:** dialog.currentColor()
> 
> **论证:**不需要论证
> 
> **返回:**返回 QColor 对象

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
        self.setGeometry(100, 100, 500, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a QColorDialog object
        dialog = QColorDialog(self)

        # setting current color
        dialog.setCurrentColor(Qt.red)

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

        color = Qt.darkBlue

        # setting graphic effect to the label
        graphic = QGraphicsColorizeEffect(self)

        # setting color to the graphic
        graphic.setColor(color)

        # setting graphic to the label
        label.setGraphicsEffect(graphic)

        # getting the current color
        value = dialog.currentColor()

        # setting text to the label
        label.setText("Color : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/1442f2ca34b9b01c70dc6cf9d34350a6.png)
![](img/394966d82d2f3b2bb7b995bdd9813068.png)