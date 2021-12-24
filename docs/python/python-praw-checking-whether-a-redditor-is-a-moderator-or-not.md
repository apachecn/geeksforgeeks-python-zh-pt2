# Python PRAW–检查 redditor 是否是版主

> 原文:[https://www . geesforgeks . org/python-praw-checking-a-redditor-是-版主-还是-不是/](https://www.geeksforgeeks.org/python-praw-checking-whether-a-redditor-is-a-moderator-or-not/)

在 Reddit 中，redditor 是给用户的术语。版主是一个 redditor，其任务是调节一个子循环。这里我们将看到如何检查一个 redditor 是否是任何子循环的版主。我们将使用`Redditor`类的`is_mod`属性来检查 redditor 是否是版主。

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

print("Is " + redditor_name + " a moderator? : " +
      str(redditor.is_mod))
```

**输出:**

```py
Is spez a moderator? : True
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

print("Is " + redditor_name + " an employee of Reddit? : " +
      str(redditor.is_mod))
```

**输出:**

```py
Is AutoModerator a moderator? : True
```