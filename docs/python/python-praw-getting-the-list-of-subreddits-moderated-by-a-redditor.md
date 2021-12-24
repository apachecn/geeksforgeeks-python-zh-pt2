# Python PRAW–获取由 redditor 主持的子循环列表

> 原文:[https://www . geesforgeks . org/python-praw-get-list-of-subreddit-由 a-redditor 主持/](https://www.geeksforgeeks.org/python-praw-getting-the-list-of-subreddits-moderated-by-a-redditor/)

在 Reddit 中，redditor 是给用户的术语。版主是负责子版块内容审核的编辑者。这里我们将看到如何获取 redditor 正在调节的所有子循环。我们将使用`Redditor`类的`moderated()`方法来获取 redditor 的调节子循环列表。

## 主持人()

> **语法:**redditor . dumited()
> 
> **参数:**无
> 
> **返回:**子类对象列表

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

# fetching the list of moderated subreddits
subreddits = redditor.moderated()

# printing the name of the subreddits
for subreddit in subreddits:
    print(subreddit)
```

**输出:**

```py
announcements
blog
programming
HighQualityGifs
OutOfTheLoop
SubredditDrama
business
PartyParrot
modnews
Layer
redditdev
redesign
hero0fwar
reddit_fact_check
yourweek
spez
metaskreddit
hipmunk
guild
modprogramming

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

# fetching the list of moderated subreddits
subreddits = redditor.moderated()

# counting the number od subreddits moderated
print(redditor_name + " is a moderator of " + str(len(subreddits)) + " number of subreddits.")
```

**输出:**

```py
AutoModerator is a moderator of 10024 number of subreddits.

```