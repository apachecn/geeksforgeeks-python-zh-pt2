# 使用 Python 中的 Fast2SMS API 向任何手机号码发送短信

> 原文:[https://www . geesforgeks . org/send-text-messages-to-any-mobile-number-use-fastwams-API-in-python/](https://www.geeksforgeeks.org/send-text-messages-to-any-mobile-number-using-fast2sms-api-in-python/)

这篇文章将讲述我们如何使用 Python 发送文本消息。我们将使用 [**快速 2 毫秒应用编程接口**](https://www.fast2sms.com/dashboard/sms/bulk) 发送消息。您不需要为此安装任何 Python 包。

首先，你需要一个**fast 2s**账户。您可以在这里从[注册快速 2 毫秒。现在，转到](https://www.fast2sms.com/) [**开发应用编程接口**](https://www.fast2sms.com/dashboard/dev-api) 选项，复制应用编程接口授权密钥。该应用编程接口密钥是由 Fast2SMS 生成的，但是，如果您愿意，您可以重新生成该应用编程接口密钥。现在，您所要做的就是用您的应用编程接口密钥、消息、收件人等向 Fast2SMS 应用编程接口发出一个 **POST** 请求。它会给你发短信。

所以，要向 API 发出请求，我们需要使用[](https://www.geeksforgeeks.org/python-requests-tutorial/)**模块，要读取 API 返回的数据，我们需要 [**json**](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/) 模块。首先，让我们导入它们。**

## **蟒蛇 3**

```py
# import required module
import requests
import json
```

**现在，我们将创建两个字典，一个用于短信数据，另一个用于标题。**

 **## 巨蟒

```py
# mention url
url = "https://www.fast2sms.com/dev/bulk"

# create a dictionary
my_data = {
     # Your default Sender ID
    'sender_id': 'FSTSMS', 

     # Put your message here!
    'message': 'This is a test message', 

    'language': 'english',
    'route': 'p',

    # You can send sms to multiple numbers
    # separated by comma.
    'numbers': '9999999999, 7777777777, 6666666666'    
}

# create a dictionary
headers = {
    'authorization': 'YOUR API KEY HERE',
    'Content-Type': "application/x-www-form-urlencoded",
    'Cache-Control': "no-cache"
}
```** 

**现在，我们准备将数据发布到应用编程接口。**

 **## 蟒 3

```py
# make a post request
response = requests.request("POST",
                            url,
                            data = my_data,
                            headers = headers)
#
load json data from source
returned_msg = json.loads(response.text)

# print the send message
print(returned_msg['message'])
```** 

****输出:****

```py
['Message sent successfully to NonDND numbers']
```

**如果消息发送成功，它将打印成功消息。您的手机号码将与您的信息一起显示给收件人。**

**如果出现错误，它将打印错误消息。**

****例如**，如果您的 API 密钥被更改或您输入了错误的 API 密钥，将打印以下错误信息。**

```py
Invalid Authentication, Check Authorization Key
```