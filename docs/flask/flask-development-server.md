# 烧瓶开发服务器

> 原文:[https://www.geeksforgeeks.org/flask-development-server/](https://www.geeksforgeeks.org/flask-development-server/)

**什么是烧瓶？**

[Flask](https://www.geeksforgeeks.org/python-introduction-to-web-development-using-flask/) 是一个基于 python 的微 web 框架。微框架通常是一个很少甚至没有对库的外部依赖的框架。尽管作为一个微框架，Flask 和其他任何网络框架一样有效，因为它有大量可用的 python 库，如 SQLAlchemy、Flask-Migrate 等。在本文中，我们将讨论什么是开发服务器以及为什么使用它。

**什么是开发服务器？**

开发服务器是开发人员用于开发、测试程序、网站、软件或应用程序的服务器。它提供运行时环境以及程序调试和开发所需的所有硬件/软件实用程序。

您可以使用开发服务器来检查您的 web 应用程序是否按预期工作。在 flask 中，当调试设置设置为 true 时，您也可以使用开发服务器调试应用程序。

在本文中，我们将创建一个基于单页烧瓶的 web 应用程序，并解释运行开发服务器的不同方法。

**创建烧瓶网络应用程序–**

**模块安装:**要使用 pip(python 的包安装程序)安装烧瓶，请运行以下命令:

```py
pip install flask
```

**示例:**下面是一个简单的 flask 应用程序的代码，该应用程序只有一个页面，我们将使用开发服务器来检查该页面是否如预期的那样在应用程序中提供。

## app . py

```py
from flask import Flask, render_template

app = Flask(__name__)

# Debug setting set to true
app.debug = True

@app.route('/')
def index():
    return "Greetings from GeeksforGeeks"

if __name__ == '__main__':
    app.run()
```

**启动开发服务器:**使用以下命令启动烧瓶中的开发服务器。

```py
pyhton <name>.py
```

这里<name>是已经创建了 flask 应用程序实例并且存在 *app.run()* 函数的文件的名称。按照惯例，这个文件大部分被命名为 app，因此命令将显示如下。</name>

```py
python app.py
```

开发服务器将在***http://127 . 0 . 0 . 1:5000/***上打开，您将在浏览器屏幕上看到以下输出。

```py
Greetings from GeeksforGeeks
```

**延迟加载或急切加载–**使用开发服务器时，即使您在代码中引入语法错误或其他初始化错误，它也会继续运行。访问有错误的站点将显示错误的交互式调试器，而不是使服务器崩溃。这个功能叫做**懒加载**。更简单地说，在延迟加载中，即使应用程序出现问题，服务器也不会崩溃，而是加载了一个信息丰富的调试器页面。

要激活延迟加载，您可以修改命令如下:

```py
python app.py --lazy-loading
```

现在，在**急切加载**、中，如果应用程序代码或应用程序的某个可能部分存在错误，那么开发服务器不会加载交互式调试器，而是通过错误的详细追溯来失败。

要激活快速加载，您可以修改命令如下:

```py
python app.py --eager-loading
```

**参考:**T2】https://flask.palletsprojects.com/en/2.0.x/