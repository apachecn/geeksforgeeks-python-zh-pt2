# PyQt5–获取比特币价格的应用程序

> 原文:[https://www . geesforgeks . org/pyqt 5-应用程序获取比特币价格/](https://www.geeksforgeeks.org/pyqt5-application-to-get-the-price-of-bitcoin/)

在这篇文章中，我们将看到如何制作一个 PyQt5 应用程序，它可以显示比特币的实时价格。

**所需模块和安装:**

**PyQt5 :** PyQt 是跨平台 GUI 工具包 Qt 的 Python 绑定，实现为 Python 插件。PyQt 是由英国河岸计算公司开发的自由软件。

```
pip install PyQt5
```

**请求:** Requests 可以让你极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

```
pip install requests
```

**美人汤:**美人汤是一个库，可以方便的从网页上刮取信息。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

```
pip install beautifulsoup4
```

> **申请获取比特币实时价格的步骤–**
> 
> 1.创建一个窗口并设置其尺寸和标题
> 2。创建一个标签来显示价格
> 3。创建一个按钮
> 4。向按钮
> 5 添加动作。动作内借助请求获取比特币价格数据
> 6。使用靓汤将数据转换成 html 代码并找到价格保存在变量
> 7 中。更改标签的文本，将价格设置为文本

以下是实施–

```
# importing libraries
from bs4 import BeautifulSoup as BS
import requests
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("PyQt5 Bit Coin ")

        # setting geometry
        self.setGeometry(100, 100, 400, 600)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # creating label to show bit coin price
        self.label = QLabel("//BIT-COIN//", self)

        # setting geometry of label
        self.label.setGeometry(50, 150, 300, 50)

        # setting its alignment
        self.label.setAlignment(Qt.AlignCenter)

        # setting font to the label
        self.label.setFont(QFont('Times', 15))

        # setting border to the push button
        self.label.setStyleSheet("border : 3px solid black;")

        # creating push button to show current price
        button = QPushButton("Show price", self)

        # setting geometry to push button
        button.setGeometry(150, 300, 100, 40)

        # adding method to the push button
        button.clicked.connect(self.show_price)

        # setting tool tip to button
        button.setToolTip("Press to get Bit Coin Price")        

    def show_price(self):

        # url of the bit coin price
        url = "https://www.google.com/search?q = bitcoin + price"

        # getting the request from url
        data = requests.get(url)

        # converting the text
        soup = BS(data.text, 'html.parser')

        # finding metha info for the current price
        ans = soup.find("div", class_="BNeawe iBp4i AP7Wnd").text

        # setting this price to the label
        self.label.setText(ans)

# create pyqt5 app

App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-400007-1" width="640" height="960" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200417033736/PyQt5-Bit-Coin-17-04-2020-03_34_04.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200417033736/PyQt5-Bit-Coin-17-04-2020-03_34_04.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200417033736/PyQt5-Bit-Coin-17-04-2020-03_34_04.mp4)</video>