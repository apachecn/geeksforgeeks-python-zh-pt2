# Python PRAW–获取 Reddit 中评论的永久链接

> 原文:[https://www . geeksforgeeks . org/python-praw-get-the-permallink-of-a-comment-in-Reddit/](https://www.geeksforgeeks.org/python-praw-getting-the-permalink-of-a-comment-in-reddit/)

在 Reddit 中，我们可以对任何提交的内容发表评论，我们也可以评论一个评论来创建一个评论线程。每个评论都有一个永久的静态超链接。这里我们将看到如何使用 PRAW 获取评论的永久链接。我们将使用`Comment`类的`permalink`属性来获取评论的永久链接。

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

# fetching the permalink attribute
permalink = comment.permalink 

print("The permalink of the comment is : \n" + permalink)
print("\nThe complete URL of the comment is : \n" +
      "https://www.reddit.com/" + permalink)
```

**输出:**

```
The permalink of the comment is : 
/r/aww/comments/hczt0c/i_got_adopted_by_this_beautiful_pup_this_weekend/fvib7aw/

The complete URL of the comment is : 
https://www.reddit.com//r/aww/comments/hczt0c/i_got_adopted_by_this_beautiful_pup_this_weekend/fvib7aw/

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

# fetching the permalink attribute
permalink = comment.permalink 

print("The permalink of the comment is : \n" + permalink)
print("\nThe complete URL of the comment is : \n" +
      "https://www.reddit.com/" + permalink)
```

**输出:**

```
The permalink of the comment is : 
/r/redditdev/comments/hbjhnk/reddit_announces_an_upcoming_overhaul_of_how_bots/fv9qvgo/

The complete URL of the comment is : 
https://www.reddit.com//r/redditdev/comments/hbjhnk/reddit_announces_an_upcoming_overhaul_of_how_bots/fv9qvgo/

```