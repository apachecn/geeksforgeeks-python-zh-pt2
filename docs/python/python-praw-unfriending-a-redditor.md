# 蟒蛇 PRAW–解除红色编辑者的好友关系

> 原文:[https://www . geesforgeks . org/python-praw-unfriending-a-redditor/](https://www.geeksforgeeks.org/python-praw-unfriending-a-redditor/)

在 Reddit 中，redditor 是给用户的术语。Reddit 为我们提供了将 Reddit 添加为已验证用户的朋友的功能。我们也可以解除朋友关系。在这里，我们将看到如何解除好友关系。我们将使用`Redditor`类的`unfriend()`方法解除 redditor 的好友关系。

## 解除好友关系()

> **语法:**redditor . unfriendd()
> 
> **参数:**无
> 
> **返回:**无

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

redditor 的用户名是:spez

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

# before using the unfriend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))

# unfriending the redditor
redditor.unfriend()

# after using the unfriend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))
```

**输出:**

```py
Are the authenticated user and spez friends? : True
Are the authenticated user and spez friends? : False

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

# before using the unfriend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))

# unfriending the redditor
redditor.unfriend()

# after using the unfriend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))
```

**输出:**

```py
Are the authenticated user and AutoModerator friends? : True
Are the authenticated user and AutoModerator friends? : False

```