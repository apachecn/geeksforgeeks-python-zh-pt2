# 如何在 PyQt5 中移除 Qlistwidget 中的所有项目？

> 原文:[https://www . geeksforgeeks . org/如何移除所有物品-in-a-qlistwigwidget-in-pyqt 5/](https://www.geeksforgeeks.org/how-to-remove-all-items-in-a-qlistwidget-in-pyqt5/)

**先决条件:**

*   [PyQt5](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/)
*   [QListWidget](https://www.geeksforgeeks.org/pyqt5-qlistwidget-python/)

Python 提供了如此多的选项来开发 GUI 应用程序，PyQt5 就是其中之一。PyQt5 是一个跨平台的 GUI 工具包，是一组针对 Qt v5 的 python 绑定。由于该库提供的工具和简单性，人们可以非常容易地开发交互式桌面应用程序。

在本文中，我们将学习如何在 PyQt5 中移除 QlistWidget 中的所有项目。为了实现所需的功能，即使用 Python 中的 Qlistwidget 来清理窗口或删除所有元素，使用了它的 clear()方法。

**语法:**

```
clear()
```

### 方法

*   导入模块
*   创建 QListWidget
*   添加标题和按钮
*   添加当按钮被按下时删除列表中所有项目的机制
*   商店橱窗

**程序:**

## 蟒蛇 3

```
# Import Module
import sys
from PyQt5.QtWidgets import *

class ListBox(QWidget):

    def __init__(self):
        super().__init__()

        self.initUI()

    def initUI(self):
        # Vertical box layout
        vbox = QVBoxLayout(self)

        # Horizontal box layout
        hbox = QHBoxLayout()

        # Create QlistWidget Object
        self.listWidget = QListWidget(self)

        # Add Items to QlistWidget
        self.listWidget.addItems(
            ['python', 'c++', 'java', 'pyqt5', 'javascript', 'geeksforgeeks'])

        # Add Push Button
        clear_btn = QPushButton('Clear', self)
        clear_btn.clicked.connect(self.clearListWidget)

        vbox.addWidget(self.listWidget)
        hbox.addWidget(clear_btn)
        vbox.addLayout(hbox)

        self.setLayout(vbox)

        # Set geometry
        self.setGeometry(300, 300, 350, 250)

        # Set window title
        self.setWindowTitle('QListWidget')

        # Display QlistWidget
        self.show()

    def clearListWidget(self):
        self.listWidget.clear()

if __name__ == '__main__':
    app = QApplication(sys.argv)

    # Call ListBox Class
    ex = ListBox()

    # Close the window
    sys.exit(app.exec_())
```

**输出:**

<video class="wp-video-shortcode" id="video-559871-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210214114755/FreeOnlineScreenRecorderProject12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210214114755/FreeOnlineScreenRecorderProject12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210214114755/FreeOnlineScreenRecorderProject12.mp4)</video>