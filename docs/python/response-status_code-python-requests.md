# 响应.状态 _ 代码–Python 请求

> 原文:[https://www . geesforgeks . org/response-status _ code-python-requests/](https://www.geeksforgeeks.org/response-status_code-python-requests/)

**响应状态码**返回一个数字，表示状态(200 表示正常，404 表示未找到)。Python 请求通常用于从特定资源 URI 获取内容。每当我们通过 Python 向指定的 URI 发出请求时，它都会返回一个响应对象。现在，这个响应对象将用于访问某些特性，如内容、标题等。本文围绕如何检查响应对象中的**响应状态码**展开。要了解有关 HTTP 状态代码的更多信息，请访问–[HTTP 状态代码|成功响应](https://www.geeksforgeeks.org/http-status-codes-successful-responses/)和 [HTTP 状态代码|信息响应](https://www.geeksforgeeks.org/http-status-codes-informational-responses/)。

#### 如何使用 Python 请求使用 response.status_code？

为了说明 response.status_code 的用法，让我们 ping api.github.com。要运行这个脚本，您需要在您的电脑上安装 Python 和请求。

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

# print request status_code
print(response.status_code)
```

##### 示例实现–

将上述文件保存为`request.py`并使用运行

```py
Python request.py

```

##### 输出–

![response.status_code-Python-requests](img/2a0e4a427304e153ee468dfabfcb51d9.png)

检查输出中的和 **200** 分别指的是 http 响应和状态代码。

#### 高级概念

Python 中有很多库可以进行 HTTP 请求，分别是 [httplib](https://docs.python.org/2/library/httplib.html) 、[urlib](https://docs.python.org/2/library/urllib.html)、 [httplib2](https://github.com/httplib2/httplib2) 、 [treq](https://github.com/twisted/treq) 等。，但是[要求](https://2.python-requests.org//en/master/)是最好的一个，有很酷的功能。如果请求的任何属性显示为空，请使用以下属性检查状态代码。

```py
requests.status_code
```

如果状态码不在 200-29 的范围内。您可能需要检查用于发出请求的方法 begin 您请求资源的 url。