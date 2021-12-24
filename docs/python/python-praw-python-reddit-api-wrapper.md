# Python | PRAW–Python Reddit API 包装器

> 原文:[https://www . geesforgeks . org/python-praw-python-Reddit-API-wrapper/](https://www.geeksforgeeks.org/python-praw-python-reddit-api-wrapper/)

**PRAW**(Python Reddit API Wrapper)是一个 Python 模块，提供对 Reddit 的 API 的简单访问。PRAW 很容易使用，并且遵循所有的 [Reddit 的 API 规则](https://github.com/reddit-archive/reddit/wiki/API)。
关于 PRAW 的文件位于[这里](http://praw.readthedocs.io/)。
**先决条件** :

*   Python 编程的基本技能
*   Reddit 基础知识:Reddit 是一个基于人们兴趣的社区网络。这些社区中的每一个都被称为子社区。用户可以订阅多个子页面来发布、评论和互动。
*   红迪网账户

要安装 PRAW，我们在终端/命令提示符下运行以下 pip 脚本。

```
pip install praw
```

安装 PRAW 后，我们需要导入它:

## 蟒蛇 3

```
import praw
```

导入 PRAW 后，我们需要实例化它。有两种类型的 PRAW 实例:

*   **只读实例:**使用只读实例，我们只能从 Reddit 中检索公共信息。来自某个子分类的前 10 篇文章之类的信息。我们不能发布这方面的材料。
*   **授权实例:**有了授权实例，我们可以做任何一个普通的 reddit 账号可以做的事情。评论、发帖、转发、投票等行为。可以执行。

**创建只读实例:**

## 蟒蛇 3

```
reddit = praw.Reddit(client_id ='my client id',
                     client_secret ='my client secret',
                     user_agent ='my user agent')

# to verify whether the instance is read-only instance or not
print(reddit.read_only)
```

输出:

```
True
```

**创建授权实例:**

## 蟒蛇 3

```
reddit = praw.Reddit(client_id ='my client id',
                     client_secret ='my client secret',
                     user_agent ='my user agent',
                     username ='my username',
                     password ='my password')

# to verify whether the instance is authorized instance or not
print(reddit.read_only)
```

输出:

```
False
```

切换回只读模式:

## 蟒蛇 3

```
reddit.read_only = True
```

现在让我们看看使用 PRAW 可以实现的一些操作:

*   **访问子循环:**在 reddit 中，有多个被称为子循环的社区。我们可以使用 subred dt 方法获得一个 subred dt 实例。

## 蟒蛇 3

```
subreddit = reddit.subreddit('GRE')

# display the subreddit name
print(subreddit.display_name)

# display the subreddit title
print(subreddit.title)      

# display the subreddit description
print(subreddit.description)
```

*   输出:

```
GRE
GRE
#/r/GRE  

This subreddit is for discussion of the GRE (Graduate Record Examination). If you're studying for the GRE, or can help people who are studying for the GRE, you're in the right place!

-----

#Rules

- You must read and follow the rules! 
https://www.reddit.com/r/gre/about/rules

-----
```

*   **访问提交:**在一个子循环中有多个帖子提交。我们可以在提交实例中迭代提交。Reddit 为我们提供了多种对提交内容进行排序的方法:
    *   上升的
    *   新的
    *   热的
    *   镀金的
    *   有争议的
    *   顶端
*   **访问 Redditor:** 在 Reddit 中，用户被称为 Redditor。我们可以使用 redditor 方法获取 redditor 实例。在这个方法中，我们传递 redditor 的用户名。

## 蟒蛇 3

```
# let the redditor be "AutoModerator"
redditor = reddit.redditor('AutoModerator')

# display AutoModerator's karma
print(redditor.link_karma)
```

*   输出:

```
6554
```