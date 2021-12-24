# 烧瓶应用程序路由

> 原文:[https://www.geeksforgeeks.org/flask-app-routing/](https://www.geeksforgeeks.org/flask-app-routing/)

**应用程序路由**意味着将网址映射到一个特定的函数，该函数将处理该网址的逻辑。现代网络框架使用更有意义的网址来帮助用户记住网址，并简化导航。

**示例:**在我们的应用程序中，URL(“/”)与根 URL 相关联。因此，如果我们网站的域名是 www.example.org，并且我们想在“www.example.org/hello”中添加路由，我们会使用“/hello”。

为了将一个函数绑定到一个网址路径，我们使用 *app.route* 装饰器。在下面的例子中，我们已经在烧瓶中实现了上述路由。

## main.py

```py
from flask import Flask

app = Flask(__name__)

# Pass the required route to the decorator.
@app.route("/hello")
def hello():
    return "Hello, Welcome to GeeksForGeeks"

@app.route("/")
def index():
    return "Homepage of GeeksForGeeks"

if __name__ == "__main__":
    app.run(debug=True)
```

hello 函数现在映射了“/hello”路径，我们得到了在浏览器上呈现的函数输出。

**运行应用程序的步骤:**使用以下命令运行应用程序。

```py
python main.py
```

**输出:**打开浏览器，访问*127 . 0 . 0 . 1:5000/你好*，会看到如下输出。

![](img/0777d4898264ac2e4b493e4b3acceebc.png)

**动态 URL–**我们也可以通过使用 URL 中的变量来构建动态 URL。要给网址添加变量，使用<变量名>规则。该函数然后接收<变量名称>作为关键字参数。

**示例:**考虑以下示例来演示动态 URL。

## main.py

```py
from flask import Flask

app = Flask(__name__)

@app.route('/user/<username>')
def show_user(username):
    # Greet the user
    return f'Hello {username} !'

# Pass the required route to the decorator.
@app.route("/hello")
def hello():
    return "Hello, Welcome to GeeksForGeeks"

@app.route("/")
def index():
    return "Homepage of GeeksForGeeks"

if __name__ == "__main__":
    app.run(debug=True)
```