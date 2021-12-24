# 响应.请求–Python 请求

> 原文:[https://www . geesforgeks . org/response-request-python-requests/](https://www.geeksforgeeks.org/response-request-python-requests/)

**response.request** 返回请求该响应的请求对象。Python 请求通常用于从特定资源 URI 获取内容。每当我们通过 Python 向指定的 URI 发出请求时，它都会返回一个响应对象。现在，这个响应对象将用于访问某些特性，如内容、标题等。本文围绕如何检查响应对象中的**响应请求**展开。

#### 如何使用 Python 请求使用 response.request？

为了说明 response.request 的用法，让我们 ping api.github.com。要运行这个脚本，您需要在您的电脑上安装 Python 和请求。

##### 先决条件–

*   [下载并安装 Python 3 最新版本](https://www.geeksforgeeks.org/download-and-install-python-3-latest-version/)
*   [如何在 Python 中安装请求–对于 windows、linux、mac](https://www.geeksforgeeks.org/how-to-install-requests-in-python-for-windows-linux-mac/)

##### 示例代码–

```py
# import requests module
import requests

# Making a get request
response = requests.get('https://api.github.com/')

# print response
print(response)

# print request object
print(response.request)
```

##### 示例实现–

将上述文件保存为`request.py`并使用运行

```py
Python request.py

```

##### 输出–

![response.request-Python-requests](img/4f3c4f93851d33aee4aae173ff222779.png)

检查输出中的**<preparedrequest></preparedrequest>**分别引用了 HttpResponse 和 HttpRequest 对象。

#### 高级概念

Python 中有很多库可以进行 HTTP 请求，分别是 [httplib](https://docs.python.org/2/library/httplib.html) 、[urlib](https://docs.python.org/2/library/urllib.html)、 [httplib2](https://github.com/httplib2/httplib2) 、 [treq](https://github.com/twisted/treq) 等。，但是[要求](https://2.python-requests.org//en/master/)是最好的一个，有很酷的功能。如果请求的任何属性显示为空，请使用以下属性检查状态代码。

```py
requests.status_code
```

如果状态码不在 200-29 的范围内。您可能需要检查用于发出请求的方法 begin 您请求资源的 url。