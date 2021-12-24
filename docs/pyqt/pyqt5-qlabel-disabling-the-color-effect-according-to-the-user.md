# PyQt5 QLabel–根据用户禁用颜色效果

> 原文:[https://www . geesforgeks . org/pyqt 5-qlabel-根据用户禁用颜色效果/](https://www.geeksforgeeks.org/pyqt5-qlabel-disabling-the-color-effect-according-to-the-user/)

在本文中，我们将看到如何根据用户指令禁用标签的颜色效果，以便当用户选中单选按钮时，颜色效果应该消失，而当用户取消选中单选按钮时，它应该再次出现。

> 为此，我们必须执行以下操作:
> 
> 1.创建标签
> 2。创建一个颜色效果对象，并将其设置为标签
> 3。创建单选按钮
> 4。向单选按钮
> 5 添加动作。在动作检查中，如果单选按钮被选中，则选中使颜色效果禁用
> 6。否则启用颜色效果

为了使颜色效果禁用和启用，我们使用`setEnable`方法。

> **语法:**color _ effect . set enabled(False)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**不返回

下面是实现

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

        # making background color light yellow
        self.setStyleSheet("background : lightyellow;")

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

        # creating a color effect
        self.color_effect = QGraphicsColorizeEffect()

        # setting color to color effect
        self.color_effect.setColor(Qt.darkBlue)

        # adding color effect to the label
        label.setGraphicsEffect(self.color_effect)

        # creating a radio button
        self.button = QRadioButton("Disable color filter", self)

        # setting geometry
        self.button.setGeometry(200, 200, 300, 30)

        # adding action to the button
        self.button.clicked.connect(self.do_something)

    # action called by the radio button
    def do_something(self):
        # radio is checked ?
        if self.button.isChecked() == True:
            # making color effect disable
            self.color_effect.setEnabled(False)

        else:
            # making color color effect enable
            self.color_effect.setEnabled(True)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-408805-1" width="640" height="428" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200507014024/Python-07-05-2020-01_36_28.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200507014024/Python-07-05-2020-01_36_28.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200507014024/Python-07-05-2020-01_36_28.mp4)</video>