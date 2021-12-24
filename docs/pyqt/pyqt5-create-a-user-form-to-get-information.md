# pyqt 5–创建用户表单以获取信息

> 原文:[https://www . geesforgeks . org/pyqt 5-创建用户表单获取信息/](https://www.geeksforgeeks.org/pyqt5-create-a-user-form-to-get-information/)

在本文中，我们将看到如何在 PyQt5 中创建用户表单。用户表单基本上是一个对话框，它使用户数据输入更加可控，也更易于用户使用。有时，在创建大型用户界面应用程序时，需要创建用户表单以获取必要的信息。

> **实施步骤:**
> 1。创建一个继承 QDialog
> 2 的窗口类。添加窗口标题并设置其几何图形
> 3。创建一个 QGropBox 对象
> 4。创建线编辑获取名称，旋转框获取年龄，组合框选择度数
> 5。创建一个创建表单的方法
> 6。在创建表单方法中，创建表单布局并添加行
> 7。每一行都应该有一个标签，输入法示例名称标签和行编辑用于输入，类似的标签用于学位和年龄，组合框和旋转框用于输入。
> 8。为确定和取消状态
> 9 创建一个 QDialogButtonBox。在接受和拒绝按钮上增加动作
> 10。如果按下确定按钮，打印所有信息，如果按下取消按钮，窗口将关闭

下面是实现

## 蟒蛇 3

```py
# importing libraries
from PyQt5.QtWidgets import *
import sys

# creating a class
# that inherits the QDialog class
class Window(QDialog):

    # constructor
    def __init__(self):
        super(Window, self).__init__()

        # setting window title
        self.setWindowTitle("Python")

        # setting geometry to the window
        self.setGeometry(100, 100, 300, 400)

        # creating a group box
        self.formGroupBox = QGroupBox("Form 1")

        # creating spin box to select age
        self.ageSpinBar = QSpinBox()

        # creating combo box to select degree
        self.degreeComboBox = QComboBox()

        # adding items to the combo box
        self.degreeComboBox.addItems(["BTech", "MTech", "PhD"])

        # creating a line edit
        self.nameLineEdit = QLineEdit()

        # calling the method that create the form
        self.createForm()

        # creating a dialog button for ok and cancel
        self.buttonBox = QDialogButtonBox(QDialogButtonBox.Ok | QDialogButtonBox.Cancel)

        # adding action when form is accepted
        self.buttonBox.accepted.connect(self.getInfo)

        # adding action when form is rejected
        self.buttonBox.rejected.connect(self.reject)

        # creating a vertical layout
        mainLayout = QVBoxLayout()

        # adding form group box to the layout
        mainLayout.addWidget(self.formGroupBox)

        # adding button box to the layout
        mainLayout.addWidget(self.buttonBox)

        # setting lay out
        self.setLayout(mainLayout)

    # get info method called when form is accepted
    def getInfo(self):

        # printing the form information
        print("Person Name : {0}".format(self.nameLineEdit.text()))
        print("Degree : {0}".format(self.degreeComboBox.currentText()))
        print("Age : {0}".format(self.ageSpinBar.text()))

        # closing the window
        self.close()

    # creat form method
    def createForm(self):

        # creating a form layout
        layout = QFormLayout()

        # adding rows
        # for name and adding input text
        layout.addRow(QLabel("Name"), self.nameLineEdit)

        # for degree and adding combo box
        layout.addRow(QLabel("Degree"), self.degreeComboBox)

        # for age and adding spin box
        layout.addRow(QLabel("Age"), self.ageSpinBar)

        # setting layout
        self.formGroupBox.setLayout(layout)

# main method
if __name__ == '__main__':

    # create pyqt5 app
    app = QApplication(sys.argv)

    # create the instance of our Window
    window = Window()

    # showing the window
    window.show()

    # start the app
    sys.exit(app.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-420538-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200529015612/Python-2020-05-29-01-55-35.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200529015612/Python-2020-05-29-01-55-35.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200529015612/Python-2020-05-29-01-55-35.mp4)</video>

```py
Person Name : Geek
Degree : BTech
Age : 20
```