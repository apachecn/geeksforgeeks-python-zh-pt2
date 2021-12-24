# 使用 pdf 邮件模块

通过电子邮件发送 PDF 文件

> 原文:[https://www . geesforgeks . org/send-pdf-file-through-email-use-pdf-mail-module/](https://www.geeksforgeeks.org/send-pdf-file-through-email-using-pdf-mail-module/)

**pdf_mail** 模块是帮助你通过 Gmail 账户发送 pdf 文档的 Python 库。

### 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install pdf-mail
```

### pdf 邮件的功能

该模块只提供了将邮件从一个帐户发送到另一个帐户的单一功能。用于执行相同操作的功能是–

*   **email _ send ():** : It will send the pdf document from your Gmail account to another Gmail account.

**注意:**

*   Note that **address _ of _ file** must contain a forward slash (/).
*   You want to update the settings of Google account for sending email.

    ```py
    account.google.com -> less secure apps -> Turn on access .
    ```

下面是实现。

```py
# Importing sendpdf function  
# From pdf_mail Library   
from pdf_mail import sendpdf

# Taking input of following values
# ex-"abcd@gmail.com" 
sender_email_address = input() 

# ex-"xyz@gmail.com" 
receiver_email_address = input() 

# ex-" abcd1412" 
sendere_email_password = input()

# ex-"Heading of email"
subject_of_email = input()    

# ex-" Matter to be sent"
body_of_email = input()

# ex-"Name of file" 
filename = input()        

# ex-"C:/Users / Vasu Gupta/ "
location_of_file = input() 

# Create an object of sendpdf function 
k = sendpdf(sender_email_address, 
            receiver_email_address,
            sender_email_password,
            subject_of_email,
            body_of_email,
            filename,
            location_of_file)

# sending an email
k.email_send()
```