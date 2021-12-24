# 使用 Python 从你的 Gmail 账户发送邮件

> 原文:[https://www . geesforgeks . org/send-mail-Gmail-account-use-python/](https://www.geeksforgeeks.org/send-mail-gmail-account-using-python/)

在这里，我们将学习如何使用 Python 代码发送简单的基本邮件。Python 作为一种强大的语言，不需要任何外部库来导入，并提供了一个本地库来发送电子邮件——“SMTP 库”。“smtplib”创建一个简单邮件传输协议客户端会话对象，用于向互联网上任何有效的电子邮件 id 发送电子邮件。不同的网站使用不同的端口号。
在本文中，我们使用的是一个 Gmail 账户发送邮件。这里使用的端口号是‘587’。而且如果你想用 Gmail 以外的网站发邮件，你需要获取相应的信息。

**从 Gmail 账户发送邮件的步骤:**

1.  首先，需要导入“smtplib”库。
2.  After that, to create a session, we will be using its instance SMTP to encapsulate an SMTP connection.

    ```py
    s = smtplib.SMTP('smtp.gmail.com', 587)
    ```

    在这种情况下，您需要传递服务器位置的第一个参数和要使用的端口的第二个参数。对于 Gmail，我们使用端口号 587。

3.  出于安全原因，现在将 SMTP 连接置于 TLS 模式。传输层安全加密所有的 SMTP 命令。之后，为了安全和身份验证，您需要在登录实例中传递您的 Gmail 帐户凭据。如果您输入无效的电子邮件 id 或密码，编译器将显示验证错误。
4.  将您需要发送的消息存储在一个变量中，比如 message。使用 sendmail()实例发送您的消息。sendmail()使用三个参数: **sender_email_id、receiver_email_id 和 message _ to _ be _ send**。参数需要处于相同的顺序。

这将从您的帐户发送电子邮件。完成任务后，使用退出()终止 SMTP 会话。

```py
# Python code to illustrate Sending mail from 
# your Gmail account 
import smtplib

# creates SMTP session
s = smtplib.SMTP('smtp.gmail.com', 587)

# start TLS for security
s.starttls()

# Authentication
s.login("sender_email_id", "sender_email_id_password")

# message to be sent
message = "Message_you_need_to_send"

# sending the mail
s.sendmail("sender_email_id", "receiver_email_id", message)

# terminating the session
s.quit()
```

**向多人发送同一条信息**

如果你需要给不同的人发同样的信息。你可以用 for 循环。
例如，您有一个需要向其发送相同邮件的电子邮件 id 列表。为此，在 SMTP 会话的初始化和终止之间插入一个“for”循环。循环将依次初始化，发送电子邮件后，SMTP 会话将终止。

```py
# Python code to illustrate Sending mail 
# to multiple users 
# from your Gmail account 
import smtplib

# list of email_id to send the mail
li = ["xxxxx@gmail.com", "yyyyy@gmail.com"]

for dest in li:
    s = smtplib.SMTP('smtp.gmail.com', 587)
    s.starttls()
    s.login("sender_email_id", "sender_email_id_password")
    message = "Message_you_need_to_send"
    s.sendmail("sender_email_id", dest, message)
    s.quit()
```

**要点:**

*   该代码可以发送没有任何附件或主题的简单邮件**。**
*   **这段代码最令人惊讶的一点是，我们可以使用它发送任意数量的电子邮件，Gmail 通常会将您的邮件放在主要部分。发送的邮件通常不会被检测为垃圾邮件。**
*   **文件处理还可以用于从文件中获取电子邮件 id，并进一步用于发送电子邮件。**

****下一步:** [使用 Python 从你的 Gmail 账户发送带有附件的邮件](https://www.geeksforgeeks.org/send-mail-attachment-gmail-account-using-python/)**

**本文由**里沙布·班萨尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**