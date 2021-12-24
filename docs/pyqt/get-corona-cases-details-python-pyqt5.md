# 获取 Corona 案例详情–Python PyQt5

> 原文:[https://www . geesforgeks . org/get-corona-cases-details-python-pyqt 5/](https://www.geeksforgeeks.org/get-corona-cases-details-python-pyqt5/)

在本文中，我们将了解如何创建一个 PyQt5 应用程序，该应用程序讲述世界各地的电晕病例，即确诊病例数、患者康复的病例数以及电晕导致的总死亡人数。

> **所需模块和安装:**
> 
> **[PyQt5](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/) :** PyQt 是跨平台 GUI 工具包 Qt 的 Python 绑定，实现为 Python 插件。PyQt 是由英国河岸计算公司开发的自由软件。
> 
> **[Requests](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/):**Requests 可以让你极其轻松的发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。
> 
> **美人汤:**美人汤是一个库，可以方便的从网页上刮取信息。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

> **实施步骤:**
> 
> 1.创建一个按钮设置其几何形状
> 2。创建三个标签来显示关于总病例、恢复病例和死亡病例的信息
> 3。为每个标签设置几何图形、对齐方式和边框
> 4。向按钮
> 5 添加动作。在行动中，借助请求美化组
> 6，从网站上删除数据。将原始数据转换成 html 代码，然后过滤得到所需的输出
> 7。借助标签在屏幕上显示输出

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
from bs4 import BeautifulSoup as BS
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

        # creating label to show the total cases
        self.label_total = QLabel("Total Cases ", self)

        # setting geometry
        self.label_total.setGeometry(100, 200, 200, 40)

        # setting alignment to the text
        self.label_total.setAlignment(Qt.AlignCenter)

        # adding border to the label
        self.label_total.setStyleSheet("border : 2px solid black;")

        # creating label to show the recovered cases
        self.label_reco = QLabel("Recovered Cases ", self)

        # setting geometry
        self.label_reco.setGeometry(100, 250, 200, 40)

        # setting alignment to the text
        self.label_reco.setAlignment(Qt.AlignCenter)

        # adding border
        self.label_reco.setStyleSheet("border : 2px solid black;")

        # creating label to show death cases
        self.label_death = QLabel("Total Deaths ", self)

        # setting geometry
        self.label_death.setGeometry(100, 300, 200, 40)

        # setting alignment to the text
        self.label_death.setAlignment(Qt.AlignCenter)

        # adding border to the label
        self.label_death.setStyleSheet("border : 2px solid black;")

        # adding action to the push button
        push.clicked.connect(self.get_cases)

    # method called by push
    def get_cases(self):

        # getting the request from url
        data = requests.get("https://www.worldometers.info/coronavirus/")

        # converting the text
        soup = BS(data.text, 'html.parser')

        # finding meta info for total cases
        total = soup.find("div", class_="maincounter-number").text

        # filtering it
        total = total[1: len(total) - 2]

        # finding meta info for other numbers
        other = soup.find_all("span", class_="number-table")

        # getting recovered cases number
        recovered = other[2].text

        # getting death cases number
        deaths = other[3].text

        # filtering the data
        deaths = deaths[1:]

        self.label_total.setText("Total Cases : " + total)
        self.label_reco.setText("Recovered Cases : " + recovered)
        self.label_death.setText("Total Deaths : " + deaths)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-406376-1" width="640" height="800" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423022635/Python-23-04-2020-02_20_08.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423022635/Python-23-04-2020-02_20_08.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423022635/Python-23-04-2020-02_20_08.mp4)</video>