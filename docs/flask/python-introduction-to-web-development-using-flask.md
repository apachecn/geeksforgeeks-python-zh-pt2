# Python |使用 Flask 的 Web 开发简介

> 原文:[https://www . geeksforgeeks . org/python-web 入门-开发-使用-flask/](https://www.geeksforgeeks.org/python-introduction-to-web-development-using-flask/)

**什么是烧瓶？**
Flask 是 Python 的一个 API，允许我们构建网络应用程序。它是由阿明·罗纳奇开发的。Flask 的框架比 Django 的框架更明确，也更容易学习，因为它实现一个简单的网络应用程序的基础代码更少。网络应用程序框架或网络框架是模块和库的集合，帮助开发人员编写应用程序，而无需编写底层代码，如协议、线程管理等。Flask 基于 WSGI(Web 服务器网关接口)工具包和 Jinja2 模板引擎。

**烧瓶入门:**
安装烧瓶需要 Python 2.6 或更高版本。您可以从任何 python IDE 上的烧瓶包导入烧瓶开始。要在任何环境中安装，您可以单击下面给出的安装链接。
要测试安装是否正常，请查看下面给出的代码。

```py
# an object of WSGI application
from flask import Flask    
app = Flask(__name__)   # Flask constructor

# A decorator used to tell the application
# which URL is associated function
@app.route('/')      
def hello():
    return 'HELLO'

if __name__=='__main__':
   app.run()
```

/' URL 与`hello()`函数绑定。当 web 服务器的主页在浏览器中打开时，该函数的输出将相应地呈现出来。

通过调用`run()`函数启动烧瓶应用程序。对于代码中的任何更改，都应该手动重新启动该方法。为了克服这一点，启用了调试支持，以便跟踪任何错误。

```py
app.debug = True
app.run()
app.run(debug = True)
```

**路由:**
如今，网络框架提供路由技术，以便用户能够记住网址。直接访问网页而不从主页导航是很有用的。它是通过下面的`route()`装饰器完成的，将网址绑定到一个函数。

```py
# decorator to route URL
@app.route(‘/hello’)  

# binding to the function of route 
def hello_world():     
   return ‘hello world’
```

如果用户访问 http://localhost:5000/hello URL，hello_world()函数的输出将在浏览器中呈现。应用对象的`add_url_rule()`函数也可以用来绑定 URL 和上面例子中的函数。

```py
def hello_world():
   return ‘hello world’
app.add_url_rule(‘/’, ‘hello’, hello_world)
```

**使用烧瓶中的变量:**
烧瓶中的变量用于通过将变量部分添加到规则参数来动态构建 URL。该变量部分标记为。它作为关键字参数传递。请看下面的例子

```py
from flask import Flask
app = Flask(__name__)

# routing the decorator function hello_name
@app.route('/hello/<name>')  
def hello_name(name):
   return 'Hello %s!' % name

if __name__ == '__main__':
   app.run(debug = True)
```

将上面的示例保存为 hello.py 并从 power shell 运行。接下来，打开浏览器，输入网址 http://localhost:5000/hello/geeks forgeeks。

**输出:**

```py
Hello GeeksforGeeks!
```

在上面的示例中，route() decorator 的参数包含附加到 URL“/hello”的变量部分作为参数。因此，如果输入像 http://localhost:5000/hello/geeksforgeks 这样的 URL，那么“geeksforgeks”将作为参数传递给 hello()函数。

除了默认的字符串变量部分，还使用了其他数据类型，如 int、float 和 path(对于可以使用斜杠的目录分隔符通道)。Flask 的 URL 规则基于 Werkzeug 的路由模块。这确保了形成的网址是唯一的，并基于 Apache 制定的先例。

**示例:**

```py
from flask import Flask
app = Flask(__name__)

@app.route('/blog/<postID>')
def show_blog(postID):
   return 'Blog Number %d' % postID

@app.route('/rev/<revNo>')
def revision(revNo):
   return 'Revision Number %f' % revNo

if __name__ == '__main__':
   app.run()

# say the URL is http://localhost:5000/blog/555
```

**输出:**

```py
Blog Number 555

# Enter this URL in the browser ? http://localhost:5000/rev/1.1
Revision Number: 1.100000

```

**在 FLask 中构建网址:**
使用`url_for()`功能动态构建特定功能的网址。函数接受函数名作为第一个参数，以及一个或多个关键字参数。请看这个例子

```py
from flask import Flask, redirect, url_for
app = Flask(__name__)

@app.route('/admin')  #decorator for route(argument) function
def hello_admin():     #binding to hello_admin call
   return 'Hello Admin'    

@app.route('/guest/<guest>')
def hello_guest(guest):    #binding to hello_guest call
   return 'Hello %s as Guest' % guest

@app.route('/user/<name>')
def hello_user(name):    
   if name =='admin':  #dynamic binding of URL to function
      return redirect(url_for('hello_admin'))  
   else:
      return redirect(url_for('hello_guest', guest = name))

if __name__ == '__main__':
   app.run(debug = True)
```

要测试这一点，请保存上述代码并通过 python shell 运行，然后打开浏览器并输入以下网址:-

```py
Input: http://localhost:5000/user/admin
Output: Hello Admin 

Input: http://localhost:5000/user/ABC
Output: Hello ABC as Guest
```

上面的代码有一个名为 user(name)的函数，通过输入 URL 接受值。它检查收到的参数是否与“admin”参数匹配。如果匹配，则调用函数 hello_admin()，否则调用 hello_guest()。

Flask 支持各种 HTTP 协议，用于从指定的 URL 检索数据，这些协议可以定义为:-

| **方法** | **描述** |
| 得到 | 这用于将未加密表单中的数据发送到服务器。 |
| 头 | 向表单提供响应正文 |
| 邮政 | 将表单数据发送到服务器。服务器不缓存 POST 方法接收的数据。 |
| 放 | 用 URL 替换目标资源的当前表示形式。 |
| 删除 | 删除给定网址的目标资源 |

**处理静态文件:**
一个 web 应用程序经常需要一个静态文件，比如 javascript 或者 CSS 文件来呈现浏览器中网页的显示。通常，web 服务器被配置为设置它们，但是在开发过程中，这些文件被作为静态文件夹放在包中或模块旁边。请参见下面给出的 JavaScript 示例:

```py
from flask import Flask, render_template
app = Flask(__name__)

@app.route("/")
def index():
   return render_template("index.html")

if __name__ == '__main__':
   app.run(debug = True)
```

下面的 HTML 代码:
这将在**模板**文件夹中，它将是我们上面写的 python 文件的兄弟

```py
<html>

   <head>
      <script type = "text/javascript" 
         src = "{{ url_for('static', filename = 'hello.js') }}" ></script>
   </head>

   <body>
      <input type = "button" onclick = "sayHello()" value = "Say Hello" />
   </body>

</html>
```

`hello.js`的 JavaScript 文件为:
*该代码将位于**静态**文件夹中，该文件夹将是模板文件夹*的同级文件夹

```py
function sayHello() {
   alert("Hello World")
}
```

上面的 hello.js 文件将相应地呈现为 HTML 文件。

来自客户端网页的对象数据请求作为全局请求对象发送到服务器。然后通过导入 Flask 模块进行处理。这些属性包括表单(包含键值对)、参数(问号(？))、Cookie(包含 Cookie 名称和值)、文件(与上传文件相关的数据)和方法(当前请求)。

**Cookie:**
Cookie 是存储在客户端计算机上的一种文本文件形式，其目的是根据用户对网页的体验和统计，记忆和跟踪与客户端使用相关的数据，以改进网站。
请求对象包含 cookie 的属性。它是所有 cookie 变量及其对应值的字典对象。它还包含自身的到期时间。在 Flask 中，cookie 设置在响应对象上。参见下面给出的例子

```py
from flask import Flask
app = Flask(__name__)
@app.route('/')
def index():
   return render_template('index.html')
```

***HTML 代码为 index.html***

```py
<html>
   <body>

      <form action = "/setcookie" method = "POST">
         <p><h3>Enter userID</h3></p>
         <p><input type = 'text' name = 'nm'/></p>
         <p><input type = 'submit' value = 'Login'/></p>
      </form>

   </body>
</html>
```

***将此代码添加到上面定义的 python 文件中***

```py
@app.route('/setcookie', methods = ['POST', 'GET'])
def setcookie():
   if request.method == 'POST':
      user = request.form['nm']

   resp = make_response(render_template('cookie.html'))
   resp.set_cookie('userID', user)

   return resp

@app.route('/getcookie')
def getcookie():
   name = request.cookies.get('userID')
   return '<h1>welcome '+name+'</h1>'
```

***HTML 代码为 cookie.html***

```py
<html>
    <body>
        <a href="/getcookie">Click me to get Cookie</a>   
   </body>
</html>
```

运行上述应用程序并访问浏览器 http://localhost:5000/
上的链接表单设置为“/setcookie”，函数集包含将呈现给另一个网页的 cookie 名称 userID。“cookie.html”包含指向另一个视图函数 getcookie()的超链接，该函数在浏览器中显示该值。

**烧瓶中的会话:**
在会话中，数据存储在服务器上。它可以定义为客户端登录到服务器直到用户注销的时间间隔。它们之间的数据保存在服务器上的临时文件夹中。每个用户都被分配了一个特定的**会话标识**。会话对象是一个字典，包含与会话相关的变量的键值对。SECRET_KEY 用于将加密数据存储在 cookie 中。

**例如:**

```py
Session[key] = value   // stores the session value
Session.pop(key, None)  // releases a session variable
```

**其他重要的 Flask 功能:**
`redirect()`:用于返回一个对象的响应，并将用户重定向到另一个指定状态码的目标位置。

```py
Syntax: Flask.redirect(location, statuscode, response)
```

//location 用于重定向到想要的 URL
//statuscode 发送头值，默认 302
//response 用于发起响应。

**中止**:用于处理代码中的错误。

```py
Syntax:  Flask.abort(code)
```

代码参数可以采用以下值来相应地处理错误:

*   **400**–针对错误请求
*   **401**–用于未经认证的
*   **403**–禁止请求
*   **404**–用于未找到
*   **406**–不可接受
*   **425**–用于不支持的介质
*   **429**–请求太多

**【烧瓶中的文件上传:**
烧瓶中的文件上传非常容易。它需要一个带有 enctype 属性和 URL 处理程序的 HTML 表单，该表单获取文件并将对象保存到所需的位置。文件临时存储在服务器上，然后存储在所需的位置。
处理上传网址的 HTML 语法是:

```py
form action="http://localhost:5000/uploader" method="POST" enctype="multipart/form-data"

```

下面是 Flask 的 python 代码:

```py
from flask import Flask, render_template, request
from werkzeug import secure_filename
app = Flask(__name__)

@app.route('/upload')
def upload_file():
   return render_template('upload.html')

@app.route('/uploader', methods = ['GET', 'POST'])
def upload_file():
   if request.method == 'POST':
      f = request.files['file']
      f.save(secure_filename(f.filename))
      return 'file uploaded successfully'

if __name__ == '__main__':
   app.run(debug = True)
```

**将表单数据发送到服务器的 HTML 文件:**
HTML 格式的表单用于收集所需条目的信息，然后转发并存储在服务器上。可以要求这些人阅读或修改表格。烧瓶通过使用网址规则来提供这种便利。在下面给出的示例中，/' URL 呈现了一个具有表单的网页(student.html)。其中填充的数据被发布到“/result”URL，该 URL 会触发 result()函数。函数的作用是:将 request.form 中的表单数据收集到一个字典对象中，然后发送给 result.html。

```py
from flask import Flask, render_template, request
app = Flask(__name__)
@app.route('/')
def student():
   return render_template('student.html')

@app.route('/result', methods = ['POST', 'GET'])
def result():
   if request.method == 'POST':
      result = request.form
      return render_template("result.html", result = result)

if __name__ == '__main__':
   app.run(debug = True)
```

```py
<!doctype html>
<html>
   <body>

      <table border = 1>
         {% for key, value in result.items() %}

            <tr>
               <th> {{ key }} </th>
               <td> {{ value }} </td>
            </tr>

         {% endfor %}
      </table>

   </body>
</html>
```

```py
<html>
   <body>

      <form action = "http://localhost:5000/result" method = "POST">
         <p>Name <input type = "text" name = "Name" /></p>
         <p>Physics <input type = "text" name = "Physics" /></p>
         <p>Chemistry <input type = "text" name = "chemistry" /></p>
         <p>Maths <input type ="text" name = "Maths" /></p>
         <p><input type = "submit" value = "submit" /></p>
      </form>
   </body>
</html>
```

![](img/fa6b6e30cfca3c5dd1388cb8d3d08993.png)

**消息闪烁:**
可以定义为出现在网页上的弹出窗口或对话框，或者类似于 JavaScript 中的提醒，用来通知用户。这可以通过在烧瓶中使用 flash()方法来完成。它将消息传递给下一个模板。

```py
Syntax: flash(message, category)
```

**消息**是要显示的实际文本，**类别**是可选的，用于呈现任何错误或信息。

**示例:**

```py
from flask import Flask
app = Flask(__name__)

# /login display login form
@app.route('/login', methods = ['GET', 'POST']) 

# login function verify username and password
def login():     
   error = None

   if request.method == 'POST':
      if request.form['username'] != 'admin' or \
         request.form['password'] != 'admin':
         error = 'Invalid username or password. Please try again !'
      else:

         # flashes on successful login
         flash('You were successfully logged in') 
         return redirect(url_for('index'))
   return render_template('login.html', error = error)
```

**参考:** [烧瓶文件](http://flask.pocoo.org/docs/1.0/tutorial/)