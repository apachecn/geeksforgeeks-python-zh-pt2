# PyQt5–获取 IP 地址的图形用户界面应用程序

> 原文:[https://www . geesforgeks . org/pyqt 5-GUI-应用程序获取 ip 地址/](https://www.geeksforgeeks.org/pyqt5-gui-application-to-get-ip-address/)

在本文中，我们将看到如何制作一个简单的 PyQt5 应用程序来获取 IP 地址

[**IP 地址:**](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/) 互联网协议地址是分配给连接到使用互联网协议进行通信的计算机网络的每个设备的数字标签。IP 地址有两个主要功能:主机或网络接口识别和位置寻址。

**所需模块和安装:**

**PyQt5 :** PyQt 是跨平台 GUI 工具包 Qt 的 Python 绑定，实现为 Python 插件。PyQt 是由英国河岸计算公司开发的自由软件。
**请求:**请求可以让你极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

> **实施步骤:**
> 
> 1.创建窗口
> 2。创建按钮并设置其几何形状
> 3。创建标签并设置其几何图形、边框和对齐方式
> 4。向按钮添加动作，即当按钮被按下时，应调用动作方法
> 5。动作方法内借助请求获取数据
> 6。过滤数据得到 IP 地址
> 7。借助标签在屏幕上显示 IP 地址

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import requests
import sys

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 400, 500)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # create push button to perform function
        push = QPushButton("Press", self)

        # setting geometry to the push button
        push.setGeometry(125, 100, 150, 40)

        # creating label to show the ip
        self.label = QLabel("Press button to see your IP", self)

        # setting geometry to the push button
        self.label.setGeometry(100, 200, 200, 40)

        # setting alignment to the text
        self.label.setAlignment(Qt.AlignCenter)

        # adding border to the label
        self.label.setStyleSheet("border : 3px solid black;")

        # adding action to the push button
        push.clicked.connect(self.get_ip)

    # method called by push
    def get_ip(self):

        # getting data
        r = requests.get("http://httpbin.org / ip")

        # json data with key as origin
        ip = r.json()['origin']

        # parsing the data
        parsed = ip.split(", ")[0]

        # showing the ip in label
        self.label.setText(parsed)

        # setting font
        self.label.setFont(QFont('Times', 12))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-402581-1" width="640" height="800" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423020508/Python-23-04-2020-01_58_40.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423020508/Python-23-04-2020-01_58_40.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423020508/Python-23-04-2020-01_58_40.mp4)</video>