# PyQt5 qcolor dialog–自定义颜色计数

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcolor dialog-custom-color-count/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-custom-color-count/)

在本文中，我们将看到如何获得 QColorDialog 小部件支持的自定义颜色数量。自定义颜色由用户制作的颜色，可以在运行时通过鼠标的帮助进行设置虽然我们可以通过`setCustomColor`方法以编程方式添加自定义颜色，但默认情况下所有自定义颜色都是白色的。我们可以借助`customColor`方法得到自定义颜色。

下面是颜色对话框中自定义颜色的样子
![](img/5668aba90d16527d59b67c0bb6496733.png)

为了做到这一点，我们对 QColorDialog 对象使用`customCount`方法

> **语法**对话框. setCount()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

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

        # setting custom colors
        dialog.setCustomColor(1, Qt.red)
        dialog.setCustomColor(2, Qt.green)
        dialog.setCustomColor(3, Qt.yellow)
        dialog.setCustomColor(4, Qt.blue)

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

        # getting the custom color
        color = dialog.customColor(4)

        # setting graphic effect to the label
        graphic = QGraphicsColorizeEffect(self)

        # setting color to the graphic
        graphic.setColor(color)

        # setting graphic to the label
        label.setGraphicsEffect(graphic)

        # getting custom color count
        value = dialog.customCount()

        # setting text to the label
        label.setText("Custom Color Count : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/08647275370ac8004ec81be2e06e661d.png)

![](img/5cb65d94e3e79b56b61bcc6be557e606.png)