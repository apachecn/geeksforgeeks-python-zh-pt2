# Python PRAW–获取评论在 Reddit 上发布的时间

> 原文:[https://www . geesforgeks . org/python-praw-获取评论发布时间-reddit/](https://www.geeksforgeeks.org/python-praw-getting-the-time-when-a-comment-was-posted-on-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。在这里，我们将看到如何获取使用 PRAW 发布评论的确切时间。我们将使用`Comment`类的`created_utc`属性来获取发布评论时的 Unix 时间。

**例 1 :** 考虑以下评论:
![](img/5ac2ced6c02a3f230d506115001584a3.png)

评论的 ID 是:fvib7aw

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

# the ID of the comment
comment_id = "fvib7aw"

# instantiating the Comment class
comment = reddit.comment(comment_id)

# fetching the Unix time
unix_time = comment.created_utc 

print("The comment was posted on Unix time : " +
      str(unix_time)) 

# converting the Unix time 
print("The comment was posted on : " +
      str(datetime.fromtimestamp(unix_time))) 
```

**输出:**

```py
The comment was posted on Unix time : 1592712950.0
The comment was posted on : 2020-06-21 09:45:50

```

**例 2 :** 考虑以下评论:
![](img/aeca015f086bff05e544bc3ace86ef4d.png)

评论的 ID 是:fv9qvgo

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

# the ID of the comment
comment_id = "fv9qvgo"

# instantiating the Comment class
comment = reddit.comment(comment_id)

# fetching the Unix time
unix_time = comment.created_utc 

print("The comment was posted on Unix time : " +
      str(unix_time)) 

# converting the Unix time 
print("The comment was posted on : " +
      str(datetime.fromtimestamp(unix_time))) 
```

**输出:**

```py
The comment was posted on Unix time : 1592513850.0
The comment was posted on : 2020-06-19 02:27:30

```