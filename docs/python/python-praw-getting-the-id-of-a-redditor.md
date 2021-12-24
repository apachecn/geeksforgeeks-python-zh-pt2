# 蟒蛇 PRAW–获取红点师的身份

> 原文:[https://www . geesforgeks . org/python-praw-get-id-of-a-redditor/](https://www.geeksforgeeks.org/python-praw-getting-the-id-of-a-redditor/)

在 Reddit 中，redditor 是给用户的术语。每个 redditor 都有一个提供给他们的唯一标识。这里我们将看到如何获取一个 redditor 的 ID。我们将使用`Redditor`类的`id`属性来获取 redditor 的标识。

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

redditor 的用户名是:spez。

```
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

print("The ID of " + redditor_name + " is : " + redditor.id)
```

**输出:**

```
The ID of prez is : ejpa

```

**例 2 :** 考虑以下 redditor :
![](img/c80c93faa6b2e754176bf9034d2fa3e5.png)

redditor 的用户名是:自动编码器

```
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

print("The ID of " + redditor_name + " is : " + redditor.id)
```

**输出:**

```
The ID of AutoModerator is : 6l4z3

```