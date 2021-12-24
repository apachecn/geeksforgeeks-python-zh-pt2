# PyQt5 qcolor dialog–检查尺寸夹点属性是否启用

> 原文:[https://www . geeksforgeeks . org/pyqt 5-qcolor dialog-checking-size-grip-property-enabled-or-not/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-checking-size-grip-property-enabled-or-not/)

在本文中，我们将了解如何检查 QColorDialog 的大小夹点属性是否已启用。启用此属性时，对话框的右下角会放置一个 QSizeGrip。默认情况下，尺寸夹点处于禁用状态。我们可以借助`setSizeGripEnabled`方法设置这个属性。

为了做到这一点，我们对 QColorDialog 对象使用`isSizeGripEnabled`方法

> **语法:**对话框. dialog.isSizeGripEnabled()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

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

        # setting grip size property enabled
        dialog.setSizeGripEnabled(True)

        # creating label
        label = QLabel("Geeks for Geeks", self)

        label.setAlignment(Qt.AlignCenter)

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

        layout = dialog.layout()

        layout.addWidget(label)

        dialog.setLayout(layout)

        # checking size grip enabled
        value = dialog.isSizeGripEnabled()

        # setting text to the label
        label.setText("Size Grip Enabled : " + str(value))

        dialog.exec_()

        self.deleteLater()

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/7391e57fbf8ffaa75fd47dc9fe710051.png)