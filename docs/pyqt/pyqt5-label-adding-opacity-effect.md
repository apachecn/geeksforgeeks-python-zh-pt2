# PyQt5 标签–添加不透明度效果

> 原文:[https://www . geesforgeks . org/pyqt 5-标签-添加-不透明度-效果/](https://www.geeksforgeeks.org/pyqt5-label-adding-opacity-effect/)

在本文中，我们将了解如何为标签添加不透明效果默认情况下，标签没有不透明效果，尽管我们可以为标签创建不透明效果。不透明度是对电磁或其他类型辐射，尤其是可见光不可透过性的度量。在辐射传输中，它描述了辐射在介质中的吸收和散射，如等离子体、电介质、屏蔽材料、玻璃等。下面是带有不透明效果的标签的外观

![](img/270b5601d63bf9fabf3ad0a681415703.png)

> 为此，我们必须执行以下操作–
> 
> 1.创建标签
> 2。将几何图形设置为标签
> 3。创建一个 QGraphicsOpacityEffect 对象
> 4。借助 setGraphicsEffect 方法将此对象添加到标签中

**语法:**

```py
# creating a opacity effect
opacity_effect = QGraphicsOpacityEffect()

# adding opacity effect to the label
label.setGraphicsEffect(opacity_effect)

```

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
        self.setGeometry(100, 100, 600, 400)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating label
        label = QLabel("Label", self)

        # setting geometry to the label
        label.setGeometry(200, 100, 150, 60)

        # setting alignment to the label
        label.setAlignment(Qt.AlignCenter)

        # setting font
        label.setFont(QFont('Arial', 15))

        # setting style sheet of the label
        label.setStyleSheet("QLabel"
                            "{"
                            "border : 2px solid green;"
                            "background : lightgreen;"
                            "}")

        # creating a opacity effect
        self.opacity_effect = QGraphicsOpacityEffect()

        # setting opacity level
        self.opacity_effect.setOpacity(0.3)

        # adding opacity effect to the label
        label.setGraphicsEffect(self.opacity_effect)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/d7aaac56b9d6e1cdd3bf9ce43da815e6.png)