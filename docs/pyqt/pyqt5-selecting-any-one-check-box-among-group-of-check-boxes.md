# PyQt5–在一组复选框中选择任意一个复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-在一组复选框中选择任意一个复选框/](https://www.geeksforgeeks.org/pyqt5-selecting-any-one-check-box-among-group-of-check-boxes/)

当我们制作一个表单并且有多个复选框时。我们可以选择其中的一些，也可以只选择其中的一个，因为它们是相互矛盾的。所以图形用户界面阻止我们选择一个以上的复选框，如果我们选择一个以上的复选框，它会使其他框不被选中。

在本文中，我们将看到如何创建一组复选框，以便我们可以选择其中的任何一个。如果我们尝试选择其他复选框，它将自动取消选中其他复选框。

> **为了做到这一点，我们必须做以下工作–**
> 
> 1.创建一组复选框。
> 2。对于每个复选框，连接一个方法，以便每次复选框的状态发生变化时，都应该调用该方法。
> 3。该方法应该检查状态是否已选中，如果状态未选中，则什么也不做。
> 4。如果选中了状态，请检查调用此方法的复选框。
> 5。取消选中所有其他复选框。

下面是实现。

```py
# importing libraries
import sys
from PyQt5.QtWidgets import * 
from PyQt5.QtCore import *

# main window class
class   Window(QMainWindow):

    # constructor
    def __init__(self):
        super().__init__()

        # calling the method for widgets
        self.initUI()

    def initUI(self):

        # creating check box
        self.checkBoxNone = QCheckBox("Don't know ?", self)

        # setting geometry
        self.checkBoxNone.setGeometry(200, 150, 100, 30)

        # creating check box
        self.checkBoxA = QCheckBox("Geek", self)

        # setting geometry
        self.checkBoxA.setGeometry(200, 180, 100, 30)

        # creating check box
        self.checkBoxB = QCheckBox(" Not a geek ?", self)

        # setting geometry
        self.checkBoxB.setGeometry(200, 210, 100, 30)

        # calling the uncheck method if any check box state is changed
        self.checkBoxNone.stateChanged.connect(self.uncheck)
        self.checkBoxA.stateChanged.connect(self.uncheck)
        self.checkBoxB.stateChanged.connect(self.uncheck)

        # setting window title
        self.setWindowTitle('Python')

        # setting geometry of window
        self.setGeometry(100, 100, 600, 400)

        # showing all the widgets
        self.show()

    # uncheck method
    def uncheck(self, state):

        # checking if state is checked
        if state == Qt.Checked:

            # if first check box is selected
            if self.sender() == self.checkBoxNone:

                # making other check box to uncheck
                self.checkBoxA.setChecked(False)
                self.checkBoxB.setChecked(False)

            # if second check box is selected
            elif self.sender() == self.checkBoxA:

                # making other check box to uncheck
                self.checkBoxNone.setChecked(False)
                self.checkBoxB.setChecked(False)

            # if third check box is selected
            elif self.sender() == self.checkBoxB:

                # making other check box to uncheck
                self.checkBoxNone.setChecked(False)
                self.checkBoxA.setChecked(False)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-392119-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200330012746/Python-30-03-2020-01_26_50.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200330012746/Python-30-03-2020-01_26_50.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200330012746/Python-30-03-2020-01_26_50.mp4)</video>