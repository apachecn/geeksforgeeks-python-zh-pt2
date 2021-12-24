# PyQt5 qcolor Dialog–设置颜色对话框选项

> 原文:[https://www . geeksforgeeks . org/pyqt5-qcolor dialog-设置-颜色-对话框-选项/](https://www.geeksforgeeks.org/pyqt5-qcolordialog-setting-color-dialog-options/)

在本文中，我们将看到如何设置 QColorDialog 小部件的选项。QColorDialog 小部件基本上有三个对话框选项，下面是选项
1。**显示阿尔法通道:**允许用户选择颜色的阿尔法分量
2。**按钮:**不显示确定和取消按钮
3。 **DontUseNativeDialog :** 使用 Qt 的标准颜色对话框，而不是操作系统原生颜色对话框

为了做到这一点，我们对 QColorDialog 对象使用`setOption`方法

> **语法:**dialog . setoption(qcolor dialog。显示频道)
> 
> **自变量:**以选项对象为自变量
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

        # setting option
        dialog.setOption(QColorDialog.ShowAlphaChannel)

        # executing the dialog
        dialog.exec_()

        # creating label to display the color
        label = QLabel("GfG", self)

        # setting geometry to the label
        label.setGeometry(100, 100, 200, 60)

        # making label multi line
        label.setWordWrap(True)

        # setting stylesheet of the label
        label.setStyleSheet("QLabel"
                            "{"
                            "border : 5px solid black;"
                            "}")

        color = Qt.green

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

<video class="wp-video-shortcode" id="video-434870-1" width="640" height="556" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200620002054/Select-Color-2020-06-20-00-20-31.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200620002054/Select-Color-2020-06-20-00-20-31.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200620002054/Select-Color-2020-06-20-00-20-31.mp4)</video>