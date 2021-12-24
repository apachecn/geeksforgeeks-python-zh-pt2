# Python PRAW–检查某个 redditor 是否是 Reddit 的员工

> 原文:[https://www . geeksforgeeks . org/python-praw-checking-a-redditor-是不是-Reddit-的员工/](https://www.geeksforgeeks.org/python-praw-checking-whether-a-redditor-is-an-employee-of-reddit-or-not/)

在 Reddit 中，redditor 是给用户的术语。这里我们将看到如何检查一个 Reddit 用户是否是 Reddit 的员工。我们将使用`Redditor`类的`is_employee`属性来检查一个 redditor 是否是 Reddit 的员工。

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

reddit 的用户名是:spez，spez 是 Reddit 的创始人，所以他是 Reddit 的员工。

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

# the name of the redditor
redditor_name = "spez"

# instantiating the Redditor class
redditor = reddit.redditor(redditor_name)

print("Is " + redditor_name + " an employee of Reddit? : " +
      str(redditor.is_employee))
```

**输出:**

```
Is spez an employee of Reddit? : True
```

**例 2 :** 考虑以下 redditor :
![](img/c80c93faa6b2e754176bf9034d2fa3e5.png)

redditor 的用户名是:自动编码器

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

# the name of the redditor
redditor_name = "AutoModerator"

# instantiating the Redditor class
redditor = reddit.redditor(redditor_name)

print("Is " + redditor_name + " an employee of Reddit? : " +
      str(redditor.is_employee))
```

**输出:**

```
Is AutoModerator an employee of Reddit? : False
```