# Python PRAW–检查评论是否已在 Reddit 中编辑

> 原文:[https://www . geeksforgeeks . org/python-praw-checking-a-comment-是否已被编辑-in-reddit/](https://www.geeksforgeeks.org/python-praw-checking-whether-a-comment-has-been-edited-or-not-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。评论可以在发布后进行编辑。在这里，我们将看到如何检查一个评论是否已经被编辑或没有使用 PRAW。我们将使用`Comment`类的`edited`属性来检查评论是否被编辑过。

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

# fetching the edited attribute
edited = comment.edited 

if edited == True:
    print("The comment has been edited.")
elif edited == False:
    print("The comment has not been edited.")
```

**输出:**

```
The comment has not been edited.

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

# fetching the edited attribute
edited = comment.edited 

if edited == True:
    print("The comment has been edited.")
elif edited == False:
    print("The comment has not been edited.")
```

**输出:**

```
The comment has not been edited.

```