# PyQt5 qcolor dialog–给定点的孩子

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcolor dialog-给定点儿童/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-child-at-given-point/)

在本文中，我们将看到如何在给定的时间点获取 QColorDialog 小部件的子部件。QColorDialog 小部件由多个小部件组成，如 QLabel、QPushButton、QSpinBox 和许多其他小部件。组合这些小部件形成颜色对话框。

为了做到这一点，我们对 QColorDialog 对象使用`childAt`方法

> **语法:** dialog.childAt(x，y)
> 
> **参数:**需要两个整数参数
> 
> **返回:**返回子对象

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

        dialog.setSizeGripEnabled(True)

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

        # getting child of color dialog at point
        value = dialog.childAt(10, 10)

        # setting text to the label
        label.setText("Child at 10, 10 : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/e98ee9e8e7a129e0c7f0699dff71e1e4.png)