# 姜戈频道–介绍和基本设置

> 原文:[https://www . geesforgeks . org/django-channels-introduction-and-basic-setup/](https://www.geeksforgeeks.org/django-channels-introduction-and-basic-setup/)

[Django](https://www.geeksforgeeks.org/django-introduction-and-installation/) 是一个强大的用于 web 开发的 Python 框架。它快速、安全、可靠。通道允许 Django 项目处理 HTTP 以及异步协议，如网络套接字、MQTT、聊天程序等等。

### 频道:

通道保留了 Django 的同步行为，并添加了一层异步协议，允许用户编写完全同步、异步或两者混合的视图。通道基本上允许应用程序支持“长时间运行的连接”。它用其 **ASGI** 取代了姜戈的默认 **WSGI** 。

### 阿斯嘉:

**ASGI** (异步服务器网关接口)提供异步 Python web 服务器和应用程序之间的接口，同时支持 WSGI 提供的所有功能。

### 消费者:

A **消费者**是渠道的基本单位。它是一个支持异步和同步应用程序的事件驱动类。消费者可以运行更长时间，因此他们支持需要持久连接的 web 套接字。

在这篇文章中，我们将建立一个渠道的基本例子。我们将构建一个计算器应用程序，允许用户向服务器发送多个表达式，并通过一个持久连接接收结果。

### 环境设置:

*   为 python 应用程序创建一个虚拟环境总是一个好主意，以避免版本冲突。在终端中运行以下命令即可开始

```py
easy-install pip
python3 -m pip install virtualenv
virtualenv venv
source venv/bin/activate
```

*   现在安装**姜戈**和**通道**:

```py
pip install django
pip install channels
# On windows, try an unofficial wheel of 'Twisted' in case of dependency errors
```

### 实时计算器应用:

现在开始一个姜戈项目，创建一个名为**‘生活计算器’**

```py
django-admin startproject sampleProject
cd sampleProject
python3 manage.py startapp liveCalculator
```

的应用程序

在**样本项目/设置. py** 中，注册**频道**和**生活计算器**。

**设置:**T0】

在 sampleProject/asgi.py 中，添加 http 协议。

**asgi . py:**

## python 3

```py
import os

import django
from channels.http import AsgiHandler
from channels.routing import ProtocolTypeRouter

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'sampleProject.settings')
django.setup()

application = ProtocolTypeRouter({
  "http": AsgiHandler(),
  # Just HTTP for now. (We can add other protocols later.)
})
```