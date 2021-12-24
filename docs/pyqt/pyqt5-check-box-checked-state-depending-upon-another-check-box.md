# PyQt5–复选框选中状态取决于另一个复选框

> 原文:[https://www . geesforgeks . org/pyqt 5-复选框-选中-状态-取决于另一个-复选框/](https://www.geeksforgeeks.org/pyqt5-check-box-checked-state-depending-upon-another-check-box/)

有时在创建 GUI(图形用户界面)应用程序时，需要制作许多复选框，有些复选框依赖于前一个复选框，例如，有两个以下复选框第一个复选框是“您有笔记本电脑吗？”第二个复选框是
“你的笔记本电脑有 i7 处理器吗？”这里我们可以看到，如果第一个复选框为真，那么只有第二个复选框可以为真。

因此，为了克服这种依赖性，如果第一个复选框未被选中，我们必须停止第二个复选框以被选中。选中第一个复选框后，只有用户可以选中第二个复选框。

> **为了做到这一点，我们必须做到以下几点:**
> 
> 1.创建两个复选框。
> 2。将第二个复选框的可检查状态设置为假，即默认情况下它不能被选中。
> 3。向第一个复选框添加操作，即当第一个复选框的状态发生变化时，调用与之关联的方法。
> 4。在操作方法内部，检查是否选中了第一个复选框。
> 5。如果选中了第一个复选框，那么将第二个复选框的可勾选状态设为“真”，也就是说，现在可以选中它了。
> 6。如果第一个复选框未选中，则使第二个复选框状态为取消选中，并使其不可取消选中。

下面是实现。

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

        # creating the check-box
        self.checkbox1 = QCheckBox('Geek ?', self)

        # setting geometry of check box
        self.checkbox1.setGeometry(200, 150, 100, 40)

        # adding action to check box
        self.checkbox1.stateChanged.connect(self.allow)

        # creating the check-box
        self.checkbox2 = QCheckBox('Geeky Geek ?', self)

        # setting geometry of check box
        self.checkbox2.setGeometry(200, 180, 100, 40)

        # stooping check box to get checked
        self.checkbox2.setCheckable(False)

    # method called by checkbox1
    def allow(self):

        # checking if checkbox1 is checked ?
        if self.checkbox1.isChecked():

            # allow second check box to get checked
            self.checkbox2.setCheckable(True)

        # first check box is unchecked
        else:

            # make second check box unchecked
            self.checkbox2.setCheckState(0)

            # make second check box uncheckable
            self.checkbox2.setCheckable(False)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-394624-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200403192753/Python-03-04-2020-19_27_19.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200403192753/Python-03-04-2020-19_27_19.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200403192753/Python-03-04-2020-19_27_19.mp4)</video>