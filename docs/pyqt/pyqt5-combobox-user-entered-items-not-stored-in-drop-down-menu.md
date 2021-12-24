# PyQt5 组合框–用户输入的项目未存储在下拉菜单

中

> 原文:[https://www . geesforgeks . org/pyqt 5-combobox-用户输入-项目-未存储在下拉菜单/](https://www.geeksforgeeks.org/pyqt5-combobox-user-entered-items-not-stored-in-drop-down-menu/)

在本文中，我们将看到用户输入的项目如何不被添加到组合框中，即当用户在可编辑的组合框中插入项目时，它不会被插入到下拉列表的任何位置，默认情况下，当用户插入任何项目时，它会被插入到底部。
如果我们使用普通的，即不可编辑的组合框，用户不能向组合框中添加任何项目，但可编辑的组合框允许用户编辑项目或从项目列表中搜索项目。有时需要组合框应该是可编辑的，并且它不插入任何项目，例如在选择国家的组合框中，可编辑的组合框将有助于搜索国家，并且它不允许用户添加另一个项目。

> 为了使组合框使得用户插入的项目不会被添加到下拉列表中，我们必须执行以下操作–
> 1。创建组合框
> 2。使用设置可编辑方法
> 3 使组合框可编辑。设置组合框的插入策略为不插入
> 4。创建标签
> 5。检索插入策略并借助标签
> 显示

下面是实现–

## 蟒蛇 3

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
        geek_list = ["Geek", "Geeky Geek"]

        # adding list of items to combo box
        self.combo_box.addItems(geek_list)

        # creating editable combo box
        self.combo_box.setEditable(True)

        # setting insertion policy
        # stopping insertion
        self.combo_box.setInsertPolicy(QComboBox.NoInsert)

        # getting current insertion policy
        policy = self.combo_box.insertPolicy()

        # creating label to  print the policy
        label = QLabel("Insertion policy = " + str(policy), self)

        # setting geometry of the label
        label.setGeometry(200, 100, 200, 30)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-396833-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200413165951/screen_recorder_video_2020_13_4_16_57_38.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200413165951/screen_recorder_video_2020_13_4_16_57_38.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200413165951/screen_recorder_video_2020_13_4_16_57_38.mp4)</video>