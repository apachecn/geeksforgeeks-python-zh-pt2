# Python PRAW–检查 redditor 是否是用户的朋友

> 原文:[https://www . geesforgeks . org/python-praw-check-a-redditor-是否是用户的朋友/](https://www.geeksforgeeks.org/python-praw-check-whether-a-redditor-is-friends-with-the-user/)

在 Reddit 中，redditor 是给用户的术语。Reddit 允许经过身份验证的用户与另一个 Reddit 成为“朋友”。在这里，我们将看到如何检查 redditor 是否是经过身份验证的用户的朋友。我们将使用`Redditor`类的`is_friend`属性来检查一个 redditor 是否是认证用户的朋友。

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

redditor 的用户名是:spez。

```py
# importing the module
import praw

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

print("Is " + redditor_name + " friends with the authenticated user? : " +
      str(redditor.is_friend))
```

**输出:**

```py
Is spez friends with the authenticated user? : False

```

**例 2 :** 考虑以下 redditor :
![](img/c80c93faa6b2e754176bf9034d2fa3e5.png)

redditor 的用户名是:自动编码器

```py
# importing the module
import praw

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

print("Is " + redditor_name + " friends with the authenticated user? : " +
      str(redditor.is_friend))
```

**输出:**

```py
Is AutoModerator friends with the authenticated user? : False

```