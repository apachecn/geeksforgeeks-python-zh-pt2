# PyQt5 输入对话框| Python

> 原文:[https://www.geeksforgeeks.org/pyqt5-input-dialog-python/](https://www.geeksforgeeks.org/pyqt5-input-dialog-python/)

[PyQt5](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/) 提供了一个名为 QInputDialog 的类，用于接受用户的输入。在大多数应用程序中，会出现用户需要输入一些数据的情况，因此需要输入对话框。输入可以是字符串或文本、整数、双精度和项目类型。
**使用的方法:**
这些方法返回具有两个元素的元组——用户输入和状态，无论用户在提供所需输入后是单击“确定”(真)还是“取消”(假)按钮。

1.  **getText():** 用于从用户处获取文本值。

2.  **getInt():** 用于从用户处取整数值。

3.  **getDouble():** 用于从用户处取 Double 值。

4.  **getItem():** 用于从用户的多选中选取所选项目。

## <u>示例:</u>

让我们使用 QInputDialog 创建一个简单的应用程序，其中将出现一个主窗口，有一个按钮“继续”。点击该按钮后，将打开多个输入对话框，询问姓名、滚动、CGPA 和从语言列表中学习的编程语言。
最后，主窗口会给出一条确认消息，并附上用户提供的详细信息。
以下是代码–

## 蟒蛇 3

```
from PyQt5 import QtCore, QtGui, QtWidgets
import sys

class Ui_MainWindow(QtWidgets.QWidget):
    def setupUi(self, MainWindow):
        MainWindow.resize(422, 255)
        self.centralwidget = QtWidgets.QWidget(MainWindow)

        self.pushButton = QtWidgets.QPushButton(self.centralwidget)
        self.pushButton.setGeometry(QtCore.QRect(160, 130, 93, 28))

        # For displaying confirmation message along with user's info.
        self.label = QtWidgets.QLabel(self.centralwidget)   
        self.label.setGeometry(QtCore.QRect(170, 40, 201, 111))

        # Keeping the text of label empty initially.      
        self.label.setText("")    

        MainWindow.setCentralWidget(self.centralwidget)
        self.retranslateUi(MainWindow)
        QtCore.QMetaObject.connectSlotsByName(MainWindow)

    def retranslateUi(self, MainWindow):
        _translate = QtCore.QCoreApplication.translate
        MainWindow.setWindowTitle(_translate("MainWindow", "MainWindow"))
        self.pushButton.setText(_translate("MainWindow", "Proceed"))
        self.pushButton.clicked.connect(self.takeinputs)

    def takeinputs(self):
        name, done1 = QtWidgets.QInputDialog.getText(
             self, 'Input Dialog', 'Enter your name:')

        roll, done2 = QtWidgets.QInputDialog.getInt(
           self, 'Input Dialog', 'Enter your roll:') 

        cgpa, done3 = QtWidgets.QInputDialog.getDouble(
              self, 'Input Dialog', 'Enter your CGPA:')

        langs =['C', 'c++', 'Java', 'Python', 'Javascript']
        lang, done4 = QtWidgets.QInputDialog.getItem(
          self, 'Input Dialog', 'Language you know:', langs)

        if done1 and done2 and done3 and done4 :
             # Showing confirmation message along
             # with information provided by user.
             self.label.setText('Information stored Successfully\nName: '
                                 +str(name)+'('+str(roll)+')'+'\n'+'CGPA: '
                                 +str(cgpa)+'\nSelected Language: '+str(lang))  

             # Hide the pushbutton after inputs provided by the use.
             self.pushButton.hide()     

if __name__ == "__main__":
    app = QtWidgets.QApplication(sys.argv)
    MainWindow = QtWidgets.QMainWindow()
    ui = Ui_MainWindow()
    ui.setupUi(MainWindow)
    MainWindow.show() '

    sys.exit(app.exec_())
```