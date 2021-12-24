# PyQt5–在组合框

中获取所选项的文本

> 原文:[https://www . geeksforgeeks . org/pyqt5-获取组合框中选定项目的文本/](https://www.geeksforgeeks.org/pyqt5-getting-the-text-of-selected-item-in-combobox/)

在本文中，我们将看到如何获取文本，即在组合框中选择的当前项目的内容，为了做到这一点，我们将使用`currentText`方法。

> **语法:**组合框. currentText()
> 
> **论证:**不需要论证
> 
> **返回:**返回字符串

**实施步骤–**

1.创建组合框
2。向组合框
3 添加项目。创建按钮
4。向按钮
5 添加动作。创建标签以显示计数
5。在动作内部，借助 currentText 方法获取在组合框中选择的当前项目的内容，并将其存储在变量
6 中。借助 setText 方法在标签中显示内容变量

以下是实施–

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

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry of combo box
        self.combo_box.setGeometry(200, 150, 120, 30)

        # geek list
        geek_list = ["Geek", "Geeky Geek", "Legend Geek", "Ultra Legend Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating push button 
        button = QPushButton("Show content ", self)

        print(self.combo_box.count())

        # adding action to button
        button.pressed.connect(self.find)

        # creating label to 
        self.label = QLabel(self)

        # setting geometry of the label
        self.label.setGeometry(200, 200, 200, 30)

    def find(self):

        # finding the content of current item in combo box
        content = self.combo_box.currentText()

        # showing content on the screen though label
        self.label.setText("Content : " + content)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396229-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200410233939/Python-10-04-2020-23_39_21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200410233939/Python-10-04-2020-23_39_21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200410233939/Python-10-04-2020-23_39_21.mp4)</video>