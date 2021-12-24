# 烧瓶中的导航条

> 原文:[https://www.geeksforgeeks.org/navigation-bars-in-flask/](https://www.geeksforgeeks.org/navigation-bars-in-flask/)

跨 HTML 页面导航是一种非常常见的跨页面工作方式。客户端导航方法通常用在 HTML 中。然而，就定制而言，拥有定制的服务器端导航可以提供更大的灵活性。本文将带您了解如何使用 Flask 中的导航条集成服务器端导航。

### 烧瓶导航

该模块用于在 flask 应用程序中构建导航栏。

*   允许服务器端从一个页面导航到另一个页面。
*   帮助定义 Python 中的 HTML 类和导航项。

### 装置

要安装此模块，请在终端中键入以下命令。

```py
pip install Flask-Navigation
```

### **使用的功能**

> **导航。栏(名称，项目):**用项目定义初始化导航类的名称。
> **导航。项目(标签、网址、参数):**为每个栏分配项目或列表。标签名，它的链接页面网址和额外的参数，如参数和字典的值。

安装后，下一步是用 Navigation()初始化应用上下文，并定义要导航的基本 HTML。导航条也需要用 Bar()在代码中定义，取位置和项目列表都是导航条的参数。每个项目都输入了它的标签、网址和在网址中传递的参数。

**第一步:**导入库，添加 app 上下文，初始化导航类对象。

## 蟒蛇 3

```py
from flask import Flask, render_template
from flask_navigation import Navigation

app = Flask(__name__)
nav = Navigation(app)
```

**步骤 2:** 添加导航定义

## 蟒蛇 3

```py
# initializing Navigations
nav.Bar('top', [
    nav.Item('Home', 'index'),
    nav.Item('Gfg', 'gfg', {'page': 5}),
])
```

**步骤 3:** 添加烧瓶路线并运行应用程序。

## 蟒蛇 3

```py
@app.route('/')
def index():
    return render_template('index.html')

@app.route('/navpage')
def navpage():
    return render_template('navpage.html')

@app.route('/gfg/<int:page>')
def gfg(page):
    return render_template('gfg.html', page=page)

if __name__ == '__main__':
    app.run()
```