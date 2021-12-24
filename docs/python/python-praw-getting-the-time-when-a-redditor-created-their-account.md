# Python PRAW–获取一个 redditor 创建他们的帐户的时间

> 原文:[https://www . geeksforgeeks . org/python-praw-get-time-what-a-redditor-created-their-account/](https://www.geeksforgeeks.org/python-praw-getting-the-time-when-a-redditor-created-their-account/)

在 Reddit 中，redditor 是给用户的术语。这里我们将看到如何获取 redditor 创建其帐户的确切时间。我们将使用`Redditor`类的`created_utc`属性来获取 redditor 创建其帐户时的 Unix 时间。

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

redditor 的用户名是:spez。

```py
# importing the module
import praw
from datetime import datetime

# initialize with appropriate values
client_id = ""
client_secret = ""
username = ""
password = ""
user_agent = ""

# creating an authorized reddit instance
reddit = praw.Reddit(client_id = client_id, 
                     client_secret = client_secret, 
                     username = username, 
                     password = password,
                     user_agent = user_agent) 

# the name of the redditor
redditor_name = "spez"

# instantiating the Redditor class
redditor = reddit.redditor(redditor_name)

# fetching the Unix time of creation
unix_time = redditor.created_utc

print("The " + redditor_name + " account was created on Unix time : " +
      str(unix_time))

# converting the Unix time
print("The " + redditor_name + " account was created on : " +
      str(datetime.fromtimestamp(unix_time)))
```

**输出:**

```py
The spez account was created on Unix time : 1118030400.0
The spez account was created on : 2005-06-06 09:30:00

```

**例 2 :** 考虑以下 redditor :
![](img/c80c93faa6b2e754176bf9034d2fa3e5.png)

redditor 的用户名是:自动编码器

```py
# importing the module
import praw
from datetime import datetime

# initialize with appropriate values
client_id = ""
client_secret = ""
username = ""
password = ""
user_agent = ""

# creating an authorized reddit instance
reddit = praw.Reddit(client_id = client_id, 
                     client_secret = client_secret, 
                     username = username, 
                     password = password,
                     user_agent = user_agent) 

# the name of the redditor
redditor_name = "AutoModerator"

# instantiating the Redditor class
redditor = reddit.redditor(redditor_name)

# fetching the Unix time of creation
unix_time = redditor.created_utc

print("The " + redditor_name + " account was created on Unix time : " +
      str(unix_time))

# converting the Unix time
print("The " + redditor_name + " account was created on : " +
      str(datetime.fromtimestamp(unix_time)))
```

**输出:**

```py
The AutoModerator account was created on Unix time : 1325741068.0
The AutoModerator account was created on : 2012-01-05 10:54:28

```