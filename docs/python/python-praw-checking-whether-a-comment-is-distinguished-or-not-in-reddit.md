# Python PRAW–检查评论在 Reddit 中是否有区别

> 原文:[https://www . geesforgeks . org/python-praw-checking-a-comment-is-distinct-or-not-in-Reddit/](https://www.geeksforgeeks.org/python-praw-checking-whether-a-comment-is-distinguished-or-not-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。子评论的主持人可以将任何评论标记为已区分。在这里，我们将看到如何使用 PRAW 检查评论是否被区分。我们将使用`Comment`类的`distinguished`属性来检查注释是否被区分。

**例 1 :** 考虑以下评论:
![](img/5ac2ced6c02a3f230d506115001584a3.png)

评论的 ID 是:fvib7aw

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

# the ID of the comment
comment_id = "fvib7aw"

# instantiating the Comment class
comment = reddit.comment(comment_id)

# fetching the distinguished attribute
distinguished = comment.distinguished 

if distinguished == None:
    print("The comment is not marked distinguished.")
else:
    print("The comment has been marked distinguished.")
```

**输出:**

```
The comment is not marked distinguished.

```

**例 2 :** 考虑以下评论:
![](img/aeca015f086bff05e544bc3ace86ef4d.png)

评论的 ID 是:fv9qvgo

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

# the ID of the comment
comment_id = "fv9qvgo"

# instantiating the Comment class
comment = reddit.comment(comment_id)

# fetching the distinguished attribute
distinguished = comment.distinguished 

if distinguished == None:
    print("The comment is not marked distinguished.")
else:
    print("The comment has been marked distinguished.")
```

**输出:**

```
The comment is not marked distinguished.

```