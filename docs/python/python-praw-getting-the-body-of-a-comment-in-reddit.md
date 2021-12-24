# Python PRAW–在 Reddit 中获取评论正文

> 原文:[https://www . geesforgeks . org/python-praw-get-body-a-comment-in-Reddit/](https://www.geeksforgeeks.org/python-praw-getting-the-body-of-a-comment-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。每个评论都有一些文本信息，这就是所谓的评论正文。这里我们将看到如何使用 PRAW 获取评论的主体。我们将使用`Comment`类的`body`属性来获取注释的主体。

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

# fetching the body of the comment
body = comment.body

# printing the body of the comment
print("The body of the comment is : \n\n" + body)
```

**输出:**

```
The body of the comment is : 

I wish I could pet dogs through the screen :(

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

# fetching the body of the comment
body = comment.body

# printing the body of the comment
print("The body of the comment is : \n\n" + body)
```

**输出:**

```
The body of the comment is : 

What’s the account?

```