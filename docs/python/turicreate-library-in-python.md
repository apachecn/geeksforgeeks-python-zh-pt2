# 图用 Python 创建库

> 原文:[https://www.geeksforgeeks.org/turicreate-library-in-python/](https://www.geeksforgeeks.org/turicreate-library-in-python/)

**TuriCreate(机器学习 Python 库):**
使用 TuriCreate 可以非常轻松地制作定制的机器学习模型。你不需要成为机器学习专家就可以使用 Turi create，它有助于轻松构建添加推荐、对象检测、图像分类、图像相似性或活动分类系统。

**turi create 的优势:**

*   它很容易使用。
*   使用灵活。
*   准备将模型部署到 ios、MacOs、watchOs 和 tvOs 应用程序。
*   它最疯狂的特点之一是它可以阅读。csv(逗号分隔值)并使用机器学习模型。

**旅游支持平台创建:**

*   macOS 10.12+
*   Linux(带 glibc 2.12+)
*   Windows 10 (via WSL)=It is little tricky to install it on windows but you can install via WSL(Windows Subsystem Linux) and if does have the same error then you have to upgrade pip by using this command:
    *   pip3 安装–升级 pip
    *   系统需求
    *   Python 2.7、3.5 或更高版本(例如。3.7, 3.8)
    *   仅 Python 3.7 macOS
    *   x86_64 架构

    强烈建议使用 Conda 环境或 virtualenv，这样我们就可以在同一台机器上使用不同的 Python 解释器。

**Turicreate 使用 sframe 进行数据处理:**
**sframe**表示可扩展的数据帧。它是一个表格、列可变的数据框对象，可以扩展到大数据。它的优点之一是它是可变的。

**代码:如何使用 SFrame 加载数据:**

```py
import turicreate as tc
from turicreate import SFrame

# Let's declare a variable for loading the data
data = tc.SFrame("data.csv")

# Here data.csv is a file stored in your system
# with name = data
```

**图创建的数据结构:**

*   SFrame
*   塞拉夫
*   萨瑞