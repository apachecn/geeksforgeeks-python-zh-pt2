# Python PRAW–在 Reddit 中否决一条评论

> 原文:[https://www . geesforgeks . org/python-praw-down voting-a-comment-in-Reddit/](https://www.geeksforgeeks.org/python-praw-downvoting-a-comment-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。我们可以投赞成票，也可以投反对票。在这里，我们将看到如何使用 PRAW 否决评论。我们将使用`Comment`类的`downvote()`方法来否决评论。

## 降级()

> **语法:**向下投票()
> **参数:**无
> **返回:**无

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

print("Score before downvoting : " + str(comment.score))

# downvoting the comment
comment.downvote()

print("Score after downvoting : " + str(comment.score))
```

**输出:**

```
Score before downvoting: 25
Score after downvoting: 24

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

print("Score before downvoting : " + str(comment.score))

# downvoting the comment
comment.downvote()

print("Score after downvoting : " + str(comment.score))
```

**输出:**

```
Score before downvoting : 4
Score after downvoting : 2

```