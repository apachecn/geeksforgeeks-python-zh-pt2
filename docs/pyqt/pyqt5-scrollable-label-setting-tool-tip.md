# PyQt5 可滚动标签–设置工具提示

> 原文:[https://www . geesforgeks . org/pyqt 5-可滚动-标签-设置-工具-提示/](https://www.geeksforgeeks.org/pyqt5-scrollable-label-setting-tool-tip/)

在本文中，我们将看到如何将工具提示设置为可滚动标签。默认情况下，当我们创建一个标签时，所有的文本都在单行中，如果文本长度大于标签，额外的文本不会显示，虽然借助`setWordWrap`方法我们可以创建一个多行标签，但是如果文本超过它，它也不会显示在标签中。为了在一个小标签中显示整个文本，我们必须使标签可滚动，为此，我们必须创建自己的可滚动标签类，该类继承了允许我们使标签可滚动的 QScrollArea 类。

> 实施步骤–
> 
> 1.创建一个继承 QScrollArea
> 2 的新类。班级内部创建垂直布局
> 3。创建一个标签，使其多行，并将其添加到布局中
> 5。超越标签的设定文本和文本方法
> 6。在主窗口类中创建该类的对象，并为其设置文本
> 7。借助`setToolTip`方法为对象添加工具提示

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

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/6eeeffd2e2924cd253b9a4667d4c60ab.png)