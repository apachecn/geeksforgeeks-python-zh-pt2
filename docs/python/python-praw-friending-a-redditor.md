# 蟒蛇 PRAW–添加红点师好友

> 原文:[https://www . geesforgeks . org/python-praw-friending-a-redditor/](https://www.geeksforgeeks.org/python-praw-friending-a-redditor/)

在 Reddit 中，redditor 是给用户的术语。Reddit 为我们提供了将 Reddit 添加为已验证用户的朋友的功能。在这里，我们将看到如何与 redditor 交朋友。我们将使用`Redditor`类的`friend()`方法与红点师交朋友。

## 朋友()

> **语法:** Redditor.friend(注)
> 
> **参数:**
> 
> *   **注意:**给友情添加一个备注，需要 Reddit Premium，可选
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

# before using the friend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))

# befriending the redditor
redditor.friend()

# after using the friend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))
```

**输出:**

```py
Are the authenticated user and spez friends? : False
Are the authenticated user and spez friends? : True

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

# before using the friend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))

# befriending the redditor
redditor.friend()

# after using the friend() method
print("Are the authenticated user and " + redditor.name +
      " friends? : " + str(redditor.is_friend))
```

**输出:**

```py
Are the authenticated user and AutoModerator friends? : False
Are the authenticated user and AutoModerator friends? : True

```