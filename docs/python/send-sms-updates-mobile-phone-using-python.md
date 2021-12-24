# 使用 python 向手机发送短信更新

> 原文:[https://www . geesforgeks . org/send-SMS-updates-mobile-phone-using-python/](https://www.geeksforgeeks.org/send-sms-updates-mobile-phone-using-python/)

如果您正在运行任何 python 脚本，并且希望通过短信将脚本中的定期更新发送到手机，则可以使用 SinchSMS API 发送短信。
**方法:**
在 [Sinch](https://www.sinch.com/) 上创建一个 app，获取该 app 的**键**和**秘籍**，使用以下脚本中的这些凭证向手机发送短信。
**Sinch 的限制:**
如果您没有任何积分(必须支付积分)，则只能向 Sinch 上注册的手机号码发送短信。
你可以使用 way 2 ms 给任何号码发短信(我会在另一篇文章中讨论如何使用 way 2 ms)，但是如果没有购买的积分，同样在 way 2 ms 上，你每天发送的短信也不能超过 100 条。

## 计算机编程语言

```
# python script for sending message update

import time
from time import sleep
from sinchsms import SinchSMS

# function for sending SMS
def sendSMS():

    # enter all the details
    # get app_key and app_secret by registering
    # a app on sinchSMS
    number = 'your_mobile_number'
    app_key = 'your_app_key'
    app_secret = 'your_app_secret'

    # enter the message to be sent
    message = 'Hello Message!!!'

    client = SinchSMS(app_key, app_secret)
    print("Sending '%s' to %s" % (message, number))

    response = client.send_message(number, message)
    message_id = response['messageId']
    response = client.check_status(message_id)

    # keep trying unless the status returned is Successful
    while response['status'] != 'Successful':
        print(response['status'])
        time.sleep(1)
        response = client.check_status(message_id)

    print(response['status'])

if __name__ == "__main__":
    sendSMS()
```

对于脚本的执行，编辑数字、app_key 和 app_secret 字段，然后简单地运行脚本。
我已经写了一个完整的脚本，通过从我们的安置网站([aitplacements.com](http://aitplacements.com/))获取最新更新，使用 sinchSMS 和 way2sms 向手机发送短信更新。GitHub 链接:[statyupdated](https://github.com/msdeep14/stayUpdated)
**练习:**创建一个 python 脚本，如果某个特定产品的价格在 Amazon.com 降到某个价格时，它会在您的手机上更新您的信息