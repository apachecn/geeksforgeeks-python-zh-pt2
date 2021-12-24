# PyQt5 可滚动标签–检索工具提示文本

> 原文:[https://www . geesforgeks . org/pyqt 5-可滚动-标签-检索-工具提示-文本/](https://www.geeksforgeeks.org/pyqt5-scrollable-label-retrieving-tooltip-text/)

在本文中，我们将看到如何获取滚动标签的工具提示文本，当我们知道我们可以通过继承一个滚动类并在其中制作标签来制作可滚动标签时。滚动标签基本上是两个小部件组合在一起，滚动区域作为基本小部件，标签作为这个类的一个组件。

> 实施步骤–
> 
> 1.创建一个继承 QScrollArea
> 2 的新类。班级内部创建垂直布局
> 3。创建一个标签，使其多行，并将其添加到布局中
> 4。在主窗口类中创建该类的对象，并为其设置文本
> 5。借助`setToolTip`方法
> 6 给物体添加刀尖。借助`toolTip`方法
> 7 检索工具提示文本。创建另一个标签来显示工具提示文本

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

# class for scrollable label
class ScrollLabel(QScrollArea):

    # constructor
    def __init__(self, *args, **kwargs):
        QScrollArea.__init__(self, *args, **kwargs)

        # making widget resizable
        self.setWidgetResizable(True)

        # making qwidget object
        content = QWidget(self)
        self.setWidget(content)

        # vertical box layout
        lay = QVBoxLayout(content)

        # creating label
        self.label = QLabel(content)

        # making label multi-line
        self.label.setWordWrap(True)

        # adding label to the layout
        lay.addWidget(self.label)

    # the setText method
    def setText(self, text):
        # setting text to the label
        self.label.setText(text)

    # getting text method
    def text(self):
        # getting text of the label
        get_text = self.label.text()

        # return the text
        return get_text

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
        # text to show in label
        text = "There are so many options provided by Python to develop GUI " \
               " There are so many options provided by Python to develop GUI" \
               " There are so many options provided by Python to develop GUI"

        # creating scroll label
        label = ScrollLabel(self)

        # setting text to the label
        label.setText(text)

        # setting geometry
        label.setGeometry(100, 100, 150, 80)

        # setting tool tip
        label.setToolTip("It is tool tip")

        # getting the tool tip
        tip = label.toolTip()

        # creating another label to show the tool tip
        result = QLabel("Tool tip : " + tip, self)

        # setting geometry to the label
        result.setGeometry(150, 200, 200, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/8eda1baf0a456be9c603751171eabd01.png)