# Python PRAW–在 Reddit 中更新评论

> 原文:[https://www . geesforgeks . org/python-praw-up voting-a-comment-in-Reddit/](https://www.geeksforgeeks.org/python-praw-upvoting-a-comment-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。我们可以投赞成票，也可以投反对票。在这里，我们将看到如何使用 PRAW 对评论进行投票。我们将使用 Comment 类的 upvote()方法对注释进行 up 投票。

## upvote()

> **语法:** upvote()
> **参数:** None
> **返回:** Nothing

**示例 1 :** 考虑以下评论:

![](img/5ac2ced6c02a3f230d506115001584a3.png)

评论的 ID 是:fvib7aw

## 蟒蛇 3

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

# the ID of the comment
comment_id = "fvib7aw"

# instantiating the Comment class
comment = reddit.comment(comment_id)

print("Score before upvoting : " + str(comment.score))

# upvoting the comment
comment.upvote()

print("Score after upvoting : " + str(comment.score))
```

**输出:**

```py
Score before upvoting : 25
Score after upvoting : 26
```

**示例 2 :** 考虑以下评论:

![](img/aeca015f086bff05e544bc3ace86ef4d.png)

评论的 ID 是:fv9qvgo

## 蟒蛇 3

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

# the ID of the comment
comment_id = "fv9qvgo"

# instantiating the Comment class
comment = reddit.comment(comment_id)

print("Score before upvoting : " + str(comment.score))

# upvoting the comment
comment.upvote()

print("Score after upvoting : " + str(comment.score))
```

**输出:**

```py
Score before upvoting : 4
Score after upvoting : 5
```