# python GUI–pyqt vs tkinter

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-GUI-pyqt-vs-tkinter/

一个**图形用户界面工具包**包含用于创建图形界面的小部件。Python 包括各种可用的接口实现，从 TkInter(它附带 Python)到各种跨平台解决方案，例如 PyQt5，它以更复杂的小部件和时尚的外观而闻名。

## **PyQt**

[PyQt](https://www.geeksforgeeks.org/python-designing-gui-applications-using-pyqt/) 是一个用于图形用户界面(GUI)小部件的工具包。它是从 Qt 的库中提取的。PyQt 是 Python 语言和 Qt 库结合的产物。PyQt 随 Qt Builder 一起推出。我们将使用它从 Qt Creator 获取 python 代码。在 qt 设计器的支持下，我们可以构建一个 GUI，然后我们可以获得该 GUI 的 python 代码。PyQt 支持包括 Windows、macOS 和 UNIX 在内的所有平台。PyQt 可以用来创建时尚的 GUI，这是一个现代且可移植的 python 框架。

**代码:**

## 蟒蛇 3

```py
# Import sys for handle the 
# exit status of the application.
import sys

# Importing required widgets
from PyQt5.QtWidgets import QApplication
from PyQt5.QtWidgets import QLabel
from PyQt5.QtWidgets import QWidget

# To create an instance of QApplication
# sys.argv contains the list of
# command-line argument
app = QApplication(sys.argv)

# To create an instance of application GUI
# root is an instance of QWidget,
# it provides all the features to
# create the application's window
root = QWidget()  

# adding title to window
root.setWindowTitle('Geeks App') 

# to place txt at the coordinates
root.move(60, 15) 

# to display text
txt = QLabel('Welcome, Geeks!', parent = root) 
txt.move(60, 15)

# Show application's GUI
root.show()

# Run application's main loop
sys.exit(app.exec_())
```

**输出:**

![](img/9514b3d7f2cd2bd9d31551140490f393.png)

一个使用 PyQt 显示文本的简单应用。

### 使用 PyQt 的优势

*   编码的多功能性——用 Qt 进行图形用户界面编程是围绕着信号和插槽的思想来创建对象之间的联系。这使得在处理图形用户界面事件时具有通用性，从而使代码基础更加流畅。
*   不仅仅是一个框架:Qt 使用各种各样的本地平台 API 进行网络、数据库开发等等。它通过一个特殊的应用编程接口提供对它们的主要访问。
*   各种 UI 组件:Qt 提供了多个小部件，如按钮或菜单，所有这些都是为所有兼容平台设计的基本界面。
*   各种学习资源:由于 PyQt 是 Python 最常用的用户界面系统之一，您可以方便地访问各种各样的文档。

### 使用 PyQt 的缺点

*   PyQt5 中缺少特定于 Python 的类文档
*   掌握 PyQt 的所有细节需要很多时间，这意味着这是一个相当陡峭的学习曲线。
*   如果应用程序不是开源的，您必须为商业许可证付费。

### tkinter

[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 是一个开源的 Python 图形用户界面(GUI)库，以其简单性而闻名。它是用 Python 预装的，所以你甚至不需要考虑安装它。这些特点使它成为初学者和中间者的首选。Tkinter 不能用于更大规模的项目。

**代码:**

## 蟒蛇 3

```py
# importing the module tkinter
import tkinter as tk

# create main window (parent window)
root = tk.Tk()

# Label() it display box
# where you can put any text. 
txt = tk.Label(root,
               text="Welcome to GeekForGeeks")

# pack() It organizes the widgets
# in blocks before placing in the parent widget.
txt.pack()

# running the main loop
root.mainloop()
```

**输出:**

![](img/52d95a7168b66348d36b9a1f838a9850.png)

使用 tkinter 显示文本的简单应用程序。

### 使用 Tkinter 的优势

*   与任何其他图形用户界面工具包相比，Tkinter 实现起来既简单又快速。
*   Tkinter 更加灵活稳定。
*   Tkinter 包含在 Python 中，所以不需要额外下载。
*   Tkinter 提供了一个简单的语法。
*   Tkinter 真的很容易理解和掌握。
*   Tkinter 提供了三种几何管理器:放置、打包和网格。这要强大得多，也容易使用。

### 使用 Tkinter 的缺点

*   Tkinter 不包括高级小部件。
*   它没有类似于 Tkinter 的 Qt Designer 的工具。
*   它没有可靠的 UI。
*   有时候，在 Tkinter 中很难调试。
*   它不是纯粹的皮托尼克。

## 【PyQt 和 Tkinter 的区别

<figure class="table">

| 号码 | **基础** | 

**PyQt**

 | 

tkinter

 |
| --- | --- | --- | --- |
| 1. | 许可证 | PyQt 在江岸商业许可和 GPL v3 ( [通用公共许可 v 3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) )下可用，如果您不希望在 GPL 兼容许可下发布您的应用程序，则必须申请商业许可。 | Tkinter 是开源的，任何商业用途都是免费的。 |
| 2. | 易于理解 | 理解 PyQt 的所有细节需要很多时间。 | Tkinter 由于库小，容易理解和掌握。 |
| 3. | 设计 | PyQt 外观现代，UI 也不错。 | Tk 的设计比较老，看起来已经过时了。 |
| 4. | 小工具 | 然后 PyQt 附带了许多强大而高级的小部件。 | TkInter 不附带高级小部件。 |
| 5. | 用户界面构建器 | PyQt 有一个 Qt Designer 工具，我们可以用它来构建图形用户界面，而不是用 Qt Designer 获取图形用户界面 python 代码。 | 它没有类似于 Tkinter 的 Qt Designer 的工具。 |
| 6. | 装置 | 默认情况下，Python 安装不包含 PyQt。 | 它包含在标准 Python 库中，因此无需单独安装。 |

</figure>