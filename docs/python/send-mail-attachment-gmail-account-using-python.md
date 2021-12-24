# 使用 Python 从您的 Gmail 帐户发送带有附件的邮件

> 原文:[https://www . geesforgeks . org/send-mail-attachment-Gmail-account-use-python/](https://www.geeksforgeeks.org/send-mail-attachment-gmail-account-using-python/)

在上一篇文章中，我们讨论了从 Gmail 帐户发送邮件的基本方法[，它没有任何主题，也没有任何附件](https://www.geeksforgeeks.org/send-mail-gmail-account-using-python/)。今天，我们将学习如何使用 Python 发送带有附件和主题的邮件。在继续之前，强烈建议您学习如何使用 Python 发送简单邮件，并学习使用 Python 的“smtplib”库的基础知识。
如果您已经阅读了上一篇文章，那么您已经了解了会话是如何创建的以及它是如何工作的。现在，您需要学习附加一个文件和主题到邮件。为此，您需要导入一些 Python 本机库。从这些库中，您需要导入我们的程序中使用的工具。

**从 Gmail 账户发送带附件邮件的步骤:**

1.  For adding an attachment, you need to import:
    *   导入 smtplib
    *   从 email.mime.multipart 导入 MIMEMultipart
    *   来自 email.mime.text 导入 MIMEText
    *   从 email.mime.base 导入 MIMEBase
    *   来自电子邮件导入编码器

    这些是一些使我们的工作变得简单的库。这些是本机库，您不需要为此导入任何外部库。

2.  首先，创建一个 MIMEMultipart 的实例，即“msg”。
3.  在创建的实例“消息”的“发件人”、“收件人”和“主题”键中提及发件人的电子邮件 id、收件人的电子邮件 id 和主题。
4.  在一个字符串中，写下你想发送的消息的正文，即 body。现在，使用 attach 函数用实例 msg 来附加主体。
5.  以“rb”模式打开您想要附加的文件。然后创建一个带有两个参数的 MIMEBase 实例。第一个是“_maintype”，另一个是“_subtype”。这是消息的所有特定于 MIME 的子类的基类。
    注意，“_maintype”是 Content-Type 主要类型(如文本或图像)，而“_subtype”是 Content-Type 次要类型(如普通或 gif 或其他媒体)。
6.  set_payload 用于将有效负载更改为编码形式。用 encode_base64 编码。最后用 MIMEMultipart 创建的实例 msg 附加文件。

完成这些步骤后，按照[上一篇文章](https://www.geeksforgeeks.org/send-mail-gmail-account-using-python/)中描述的说明创建一个会话，保护它并检查真实性，然后在发送邮件后终止会话。

```
# Python code to illustrate Sending mail with attachments
# from your Gmail account 

# libraries to be imported
import smtplib
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
from email.mime.base import MIMEBase
from email import encoders

fromaddr = "EMAIL address of the sender"
toaddr = "EMAIL address of the receiver"

# instance of MIMEMultipart
msg = MIMEMultipart()

# storing the senders email address  
msg['From'] = fromaddr

# storing the receivers email address 
msg['To'] = toaddr

# storing the subject 
msg['Subject'] = "Subject of the Mail"

# string to store the body of the mail
body = "Body_of_the_mail"

# attach the body with the msg instance
msg.attach(MIMEText(body, 'plain'))

# open the file to be sent 
filename = "File_name_with_extension"
attachment = open("Path of the file", "rb")

# instance of MIMEBase and named as p
p = MIMEBase('application', 'octet-stream')

# To change the payload into encoded form
p.set_payload((attachment).read())

# encode into base64
encoders.encode_base64(p)

p.add_header('Content-Disposition', "attachment; filename= %s" % filename)

# attach the instance 'p' to instance 'msg'
msg.attach(p)

# creates SMTP session
s = smtplib.SMTP('smtp.gmail.com', 587)

# start TLS for security
s.starttls()

# Authentication
s.login(fromaddr, "Password_of_the_sender")

# Converts the Multipart msg into a string
text = msg.as_string()

# sending the mail
s.sendmail(fromaddr, toaddr, text)

# terminating the session
s.quit()
```

 **要点:**

*   您可以使用循环向许多人发送邮件。
*   这段代码实现起来很简单。但是如果你已经在你的 gmail 账户上启用了两步验证，它将不起作用。需要先关闭两步验证。
*   使用这种方法，Gmail 将始终将您的邮件放在主要部分，发送的邮件不会是垃圾邮件。

本文由 **[里沙布·班萨尔](https://www.linkedin.com/in/rishabh-bansal-9b4b71108/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。