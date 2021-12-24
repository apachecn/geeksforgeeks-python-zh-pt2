# PyQt5 标签–添加颜色效果

> 原文:[https://www . geesforgeks . org/pyqt 5-标签-添加-颜色-效果/](https://www.geeksforgeeks.org/pyqt5-label-adding-color-effect/)

在本文中，我们将了解如何为标签添加颜色效果默认情况下，标签没有颜色效果，尽管我们可以为标签创建颜色效果。颜色效果不像背景色，它更像是我们在图片上使用的彩色滤镜，下面是带有颜色效果的标签的外观

![](img/8a5ae2b1ecad12ec5e79cae5d24876e3.png)

> 为此，我们必须执行以下操作–
> 
> 1.创建标签
> 2。将几何图形设置为标签
> 3。创建一个 QGraphicsColorizeEffect 对象
> 4。借助 setGraphicsEffect 方法将此对象添加到标签中

**语法:**

```py
# creating a color effect
color_effect = QGraphicsColorizeEffect()

# adding color effect to the label
label.setGraphicsEffect(color_effect)

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

        # maing background color cyan
        self.setStyleSheet("background : cyan;")

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

        # creating a color effect
        color_effect = QGraphicsColorizeEffect()

        # adding color effect to the label
        label.setGraphicsEffect(color_effect)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**
![](img/c6f5547e5710c657050f3f939206ba3b.png)