# PyQt5–三态复选框

> 原文:[https://www.geeksforgeeks.org/pyqt5-tri-state-check-box/](https://www.geeksforgeeks.org/pyqt5-tri-state-check-box/)

当我们创建一个复选框时，默认情况下有两种状态被选中，即“真”和“假”。但是我们可以借助`setTristate`方法给它加上既不是真也不是假的第三种状态。

下面是这三个州的样子。
![](img/75850d6c85703983fd587ffda9e080f4.png)

> **语法:**复选框。设置状态(真)
> 
> **自变量:**它以 bool 为自变量。
> 
> **执行的操作:**它将在复选框中添加第三个状态。

下面是实现。

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

        # creating the check-box
        checkbox = QCheckBox('Check Box', self)

        # setting geometry of check box
        checkbox.setGeometry(200, 150, 100, 30)

        # creating the third state
        checkbox.setTristate(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/71f6919b62b5735e36191f1fcfc4bee0.png)