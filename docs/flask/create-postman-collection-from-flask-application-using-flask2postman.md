# 使用 flask2postman

从 Flask 应用程序创建 Postman 集合

> 原文:[https://www . geeksforgeeks . org/create-postman-collection-from-flask-application-use-flask 2 postman/](https://www.geeksforgeeks.org/create-postman-collection-from-flask-application-using-flask2postman/)

**先决条件:** [邮差入门](https://www.geeksforgeeks.org/introduction-postman-api-development/)[第一款使用 Flask 的 App](https://www.geeksforgeeks.org/flask-creating-first-simple-application/)

由于 Postman 在开发领域越来越受欢迎，本文解释了一种使用用 Python 编写的命令行实用程序将它与 Flask APIs 轻松集成的方法。我们将使用 **flask2postman** 模块。但你会明白为什么这个模块？这就是为什么-

*   Generating the Postman collection from Flask APIs is a simple tool.
*   It works on the command line.
*   Provide a variety of customized, how to configure the basic website, etc.
*   Output is a JSON file, which can be easily imported into the postman.

### 装置

要安装此软件，请在终端中键入以下命令。

```
pip install flask2postman
```

### 命令

> flask postman[-h][-n NAME][-b BASE _ URL][-a][-I][-f]flask _ instance

**参数:**

> **位置参数:** flask_instance
> 
> **可选参数:**
> 
> *   **-h,–-help: 【T1] Print help and exit.**
> *   **-n name,–-NAME: 【T1] The name of the postman's collection. The default is**
> *   **App/current directory name -b BASE_URL,–-BASE _ URL BASE _ URL: 【T1] The Base url (servers) of all APIs in the postman's collection. The default is {{base_url}}.**
> *   **-a,–-all: 【T1] If the generation [option/head method](https://www.geeksforgeeks.org/http-request-methods-python-requests/) is provided.**
> *   **-s,–-static: 【T1] Generate a static file in the folder /static/{{filename}}.**
> *   **-I,–Indentation:** It is intended to be output during creation. Json () file.
> *   **-f,–Folder:** If a blueprint is provided, add a subfolder to it.

### 逐步实施

**第一步:**导入库并初始化 app 上下文

## python 3

```
from flask import Flask, render_template

app = Flask(__name__)
```

**第二步:**添加 API 路线

## python 3

```
# GET API
@app.route('/')
def index():
    return render_template('index.html')

# POST API
@app.route('/add', methods = ['POST'])
def post_data():
    return render_template('form.html')

# GET API with path param
@app.route('/gfg/<int:page>')
def gfg(page):
    return render_template('gfg.html', page=page)
```