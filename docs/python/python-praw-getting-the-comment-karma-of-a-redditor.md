# 蟒蛇 PRAW–获得红编辑的评论业力

> 原文:[https://www . geesforgeks . org/python-praw-get-the-comment-karma-of-a-redditor/](https://www.geeksforgeeks.org/python-praw-getting-the-comment-karma-of-a-redditor/)

在 Reddit 中，redditor 是给用户的术语。Reddit 因果报应是你在 Reddit 上发帖和评论得到的分数。这里我们将看到如何获取一个红编辑在红编辑上评论获得的业力。我们将使用`Redditor`类的`comment_karma`属性来获取评论因果报应。

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

print("The comment karma of " + redditor_name + " is : " +
      str(redditor.comment_karma))
```

**输出:**

```py
The comment karma of spez is : 737457

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

print("The comment karma of " + redditor_name + " is : " +
      str(redditor.comment_karma))
```

**输出:**

```py
The comment karma of AutoModerator is : 454624

```