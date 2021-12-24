# Python PRAW–检查 redditor 是否有 Reddit 溢价

> 原文:[https://www . geesforgeks . org/python-praw-check-a-redditor-has-Reddit-premium-or-not/](https://www.geeksforgeeks.org/python-praw-check-whether-a-redditor-has-reddit-premium-or-not/)

在 Reddit 中，redditor 是给用户的术语。Reddit 允许 redditors 通过付费获得额外的访问权限。在这里，我们将看到如何检查 redditor 是否有高级访问权限。我们将使用`Redditor`类的`is_gold`属性来检查 redditor 是否有高级访问权限。

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

print("Does " + redditor_name + " has an active Reddit Premium status? : " +
      str(redditor.is_gold))
```

**输出:**

```
Does spez has an active Reddit Premium status? : True

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

print("Does " + redditor_name + " has an active Reddit Premium status? : " +
      str(redditor.is_gold))
```

**输出:**

```
Does AutoModerator has an active Reddit Premium status? : True

```