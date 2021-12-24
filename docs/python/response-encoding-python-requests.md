# 响应.编码–Python 请求

> 原文:[https://www . geesforgeks . org/response-encoding-python-requests/](https://www.geeksforgeeks.org/response-encoding-python-requests/)

Python 请求通常用于从特定资源 URI 获取内容。每当我们通过 Python 向指定的 URI 发出请求时，它都会返回一个响应对象。现在，这个响应对象将用于访问某些特性，如内容、标题等。本文围绕如何检查响应对象中的**响应编码**展开。 **response.encoding** 返回用于解码 response.content 的编码。点击此处查看更多关于编码的信息–[Python Strings encoding()方法](https://contribute.geeksforgeeks.org/improve/vertical-and-horizontal-retrieval-mrt-on-tapes-5/)

#### 如何使用 Python 请求使用 response.encoding？

为了说明 response.encoding 的使用，我们来 ping 一下 Github 的 API。要运行这个脚本，您需要在您的电脑上安装 Python 和请求。

##### 先决条件–

*   [下载并安装 Python 3 最新版本](https://www.geeksforgeeks.org/download-and-install-python-3-latest-version/)
*   [如何在 Python 中安装请求–对于 windows、linux、mac](https://www.geeksforgeeks.org/how-to-install-requests-in-python-for-windows-linux-mac/)

##### 示例代码–

```py
# import requests module
import requests

# Making a get request
response = requests.get('https://api.github.com')

# print response
print(response)

# print encoding of response
print(response.encoding)
```

##### 示例实现–

将上述文件保存为`request.py`并使用运行

```py
Python request.py

```

##### 输出–

![response.encoding-Python-requests](img/842170bf1674b150df8ce6871a1a5b1b.png)

检查 **utf-8** 在输出开始时，它显示字符串使用“utf-8”编码和解码。

#### 高级概念

Python 中有很多库可以进行 HTTP 请求，分别是 [httplib](https://docs.python.org/2/library/httplib.html) 、[urlib](https://docs.python.org/2/library/urllib.html)、 [httplib2](https://github.com/httplib2/httplib2) 、 [treq](https://github.com/twisted/treq) 等。，但是[要求](https://2.python-requests.org//en/master/)是最好的一个，有很酷的功能。如果请求的任何属性显示为空，请使用以下属性检查状态代码。

```py
requests.status_code
```

如果状态码不在 200-29 的范围内。您可能需要检查用于发出请求的方法 begin 您请求资源的 url。