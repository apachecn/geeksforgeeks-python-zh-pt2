# 响应. URL–Python 请求

> 原文:[https://www.geeksforgeeks.org/response-url-python-requests/](https://www.geeksforgeeks.org/response-url-python-requests/)

**response.url** 返回响应的 url。它将显示返回内容的主网址，在所有重定向之后，如果完成的话。Python 请求通常用于从特定资源 URI 获取内容。每当我们通过 Python 向指定的 URI 发出请求时，它都会返回一个响应对象。现在，这个响应对象将用于访问某些特性，如内容、标题等。本文围绕如何检查响应对象中的**响应。**

#### 如何使用 Python 请求使用 response.url？

为了说明 response.url 的用法，让我们 ping 一下 api.github.com。要运行这个脚本，您需要在您的电脑上安装 Python 和请求。

##### 先决条件–

*   [下载并安装 Python 3 最新版本](https://www.geeksforgeeks.org/download-and-install-python-3-latest-version/)
*   [如何在 Python 中安装请求–对于 windows、linux、mac](https://www.geeksforgeeks.org/how-to-install-requests-in-python-for-windows-linux-mac/)

##### 示例代码–

```py
# import requests module
import requests

# Making a get request
response = requests.get('http://api.github.com')

# print response
print(response)

# print url
print(response.url)
```

##### 示例实现–

将上述文件保存为`request.py`并使用运行

```py
Python request.py

```

##### 输出–

![response.url-Python-requests](img/2c65ee3a7359aa343f8508fbba167a2d.png)

检查**https://api.github.com/**，它显示返回响应的 url。

#### 高级概念

Python 中有很多库可以进行 HTTP 请求，分别是 [httplib](https://docs.python.org/2/library/httplib.html) 、[urlib](https://docs.python.org/2/library/urllib.html)、 [httplib2](https://github.com/httplib2/httplib2) 、 [treq](https://github.com/twisted/treq) 等。，但是[要求](https://2.python-requests.org//en/master/)是最好的一个，有很酷的功能。如果请求的任何属性显示为空，请使用以下属性检查状态代码。

```py
requests.status_code
```

如果状态码不在 200-29 的范围内。您可能需要检查用于发出请求的方法 begin 您请求资源的 url。