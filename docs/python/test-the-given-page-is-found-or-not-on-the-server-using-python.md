# 使用 Python 测试给定页面在服务器上是否找到

> 原文:[https://www . geesforgeks . org/test-给定页面在服务器上使用 python 被发现或不被发现/](https://www.geeksforgeeks.org/test-the-given-page-is-found-or-not-on-the-server-using-python/)

在本文中，我们将编写一个 Python 脚本来测试在服务器上是否找到了给定的页面。我们将看到各种方法来做同样的事情。

**方法 1:** 使用[乌尔利布](https://www.geeksforgeeks.org/python-urllib-module/)。

Urllib 是一个包，允许你用程序访问网页。

**安装:**

```
pip install urllib
```

**进场:**

*   导入模块
*   通过读取网址将网址传递给 urllib.request()
*   现在检查包含由 urllib.request 引发的异常的 urllib.error

**实施:**

## 蟒蛇 3

```
# import module
from urllib.request import urlopen
from urllib.error import *

# try block to read URL
try:
    html = urlopen("https://www.geeksforgeeks.org/")

# except block to catch
# exception
# and identify error
except HTTPError as e:
    print("HTTP error", e)

except URLError as e:
    print("Opps ! Page not found!", e)

else:
    print('Yeah !  found ')
```

**输出:**

```
Yeah !  found
```

**方法 2:** 使用[请求](https://www.geeksforgeeks.org/python-requests-tutorial/)

Request 让你可以极其轻松地发送 HTTP/1.1 请求。该模块也没有内置 Python。要安装此软件，请在终端中键入以下命令。

**安装:**

```
pip install requests
```

**进场:**

*   导入模块
*   将 Url 传递给 requests.head()
*   如果 response.status_code == 200，则服务器已启动
*   若回应 。 状态 _ 代码 == 404 然后服务器处于关闭状态

**实施:**

## 蟒蛇 3

```
# import module
import requests

# create a function
# pass the url
def url_ok(url):

    # exception block
    try:

        # pass the url into
        # request.hear
        response = requests.head(url)

        # check the status code
        if response.status_code == 200:
            return True
        else:
            return False
    except requests.ConnectionError as e:
        return e

# driven code
url = "https://www.geeksforgeeks.org/"
url_ok(url)
```

**输出:**

```
True
```