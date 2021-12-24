# 使用 Pycharm 终端

在 Pycharm 创建一个新的 Django 项目

> 原文:[https://www . geesforgeks . org/create-a-new-django-project-in-py charm-using-py charm-terminal/](https://www.geeksforgeeks.org/create-a-new-django-project-in-pycharm-using-pycharm-terminal/)

[PyCharm](https://www.geeksforgeeks.org/django-introduction-and-installation/?ref=lbp) 是 JetBrains 开发的最流行的 Python-IDE 之一，用于执行 Python 语言的脚本。PyCharm 提供了许多有用的功能，如代码完成和检查、调试过程、对各种编程框架(如 Flask 和 Django)的支持、包管理等。PyCharm 主要用 Python 为生产性开发提供了各种工具。

[Django](https://www.geeksforgeeks.org/django-introduction-and-installation/?ref=lbp) 是一个基于 Python 的 web 框架，它允许您快速创建 web 应用程序，而没有通常使用其他框架会发现的所有安装或依赖问题。它是非常可扩展的。

让我们开始使用 PyCharm 终端在 Pycharm 中创建新的 Django 项目。

**分步实施**

**第一步:**打开你的 PyCharm，点击**新建项目**。

![](img/2945fa84997859e6d3abf573df6797f3.png)

**第二步:**选择你的目录，然后给你的项目命名，然后点击**创建**。

![](img/04cf3e86318691cca0076bd9617915b1.png)

**步骤 3 :** 然后检查你的电脑中是否安装了 Django。

在位于左下角的 pycharm 终端中键入以下命令。：

```
python -m django --version
```

如果它已经安装，那么你会看到 Django 版本安装在你的电脑。如果没有，那么可以参考[姜戈介绍和安装](https://www.geeksforgeeks.org/django-introduction-and-installation/?ref=lbp)。

![](img/a3a5fa93093d5982d1dc66f363e7dc22.png)

**第 4 步:**使用以下命令启动项目-

```
django-admin startproject firstproject
```

![](img/f738859658366130de9531dc439b7c71.png)

**步骤 5:** 将目录更改为 firstproject。

```
cd firstproject
```

![](img/d8934aa4f3f7d37051e075b506a45890.png)

**步骤 6:** 在 **cmd** 中键入以下命令启动服务器–

```
python manage.py runserver
```

![](img/13df0cd4840cc00d00392d53919cda05.png)

点击给定的网址**后(http://127.0.0.1:8000/)。**您将看到您的开发服务器，如下图所示。

![](img/e11c0080b38cd388f709cfb123dc7c4e.png)