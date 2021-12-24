# Python PRAW–在 Reddit 中检查评论者是否也是提交的作者

> 原文:[https://www . geesforgeks . org/python-praw-checking-a-commenter-是否也是 reddit 中提交内容的作者/](https://www.geeksforgeeks.org/python-praw-checking-whether-a-commenter-is-also-the-author-of-the-submission-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。投稿的作者也可以在以后评论自己的投稿。这里我们将看到如何使用 PRAW 检查评论作者是否也是提交的作者。我们将使用`Comment`类的`is_submitter`属性来检查评论作者是否也是提交的作者。

**例 1 :** 考虑以下评论:
![](img/5ac2ced6c02a3f230d506115001584a3.png)

评论的 ID 是:fvib7aw

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

# fetching the is_submitter attribute
is_submitter = comment.is_submitter 

if is_submitter == True:
    print("The commenter is also the author of the submission.")
elif is_submitter == False:
    print("The commenter is not the author of the submission.")
```

**输出:**

```py
The commenter is not the author of the submission.

```

**例 2 :** 考虑以下评论:
![](img/aeca015f086bff05e544bc3ace86ef4d.png)

评论的 ID 是:fv9qvgo

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

# fetching the is_submitter attribute
is_submitter = comment.is_submitter 

if is_submitter == True:
    print("The commenter is also the author of the submission.")
elif is_submitter == False:
    print("The commenter is not the author of the submission.")
```

**输出:**

```py
The commenter is not the author of the submission.

```