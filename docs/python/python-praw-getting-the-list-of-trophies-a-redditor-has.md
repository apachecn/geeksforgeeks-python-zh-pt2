# 蟒蛇 PRAW–获得红点师拥有的奖杯列表

> 原文:[https://www . geeksforgeeks . org/python-praw-get-the-list-of-战利品-a-redditor-has/](https://www.geeksforgeeks.org/python-praw-getting-the-list-of-trophies-a-redditor-has/)

在 Reddit 中，redditor 是给用户的术语。一个红人可以赢得一些奖杯。在这里，我们将看到如何获取 redditor 拥有的所有奖杯。我们将使用`Redditor`类的`trophies()`方法来获取 redditor 拥有的所有奖杯。

## 奖杯()

> **语法:**redditor . capsules()
> 
> **参数:**无
> 
> **返回:**类奖杯对象列表

**例 1 :** 考虑以下 redditor :
![](img/60e5b09bcc9c0497565b34e02bcac732.png)

redditor 的用户名是:spez。

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

# fetching the list of tropies
trophies = redditor.trophies()

# printing the name of the trophies
for trophy in trophies:
    print(trophy)
```

**输出:**

```
15-Year Club
Inciteful Comment
Inciteful Link
RPAN Viewer
Not Forgotten
Sequence | Editor
Spared
Alpha Tester
Inciteful Comment
Inciteful Link
redditgifts Exchanges
Inciteful Comment
Beta Team
Inciteful Link
Inciteful Comment
Inciteful Link
Inciteful Link
Inciteful Link
Inciteful Link
Best Comment
Best Comment
Reddit Premium
reddit mold
Rally Monkey
Verified Email
ComboCommenter

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

# fetching the list of tropies
trophies = redditor.trophies()

# printing the name of the trophies
for trophy in trophies:
    print(trophy)
```

**输出:**

```
Eight-Year Club
Undead | Zombie
Inciteful Comment
Inciteful Comment
Well-rounded
Inciteful Comment
Well-rounded
Well-rounded
Reddit Premium

```