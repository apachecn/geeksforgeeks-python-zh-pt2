# Python–与 PRAW 一起制作 Reddit 机器人

> 原文:[https://www . geesforgeks . org/python-making-a-Reddit-bot-with-praw/](https://www.geeksforgeeks.org/python-making-a-reddit-bot-with-praw/)

Reddit 是一个基于人们兴趣的社区网络。这些社区中的每一个都被称为子社区。用户可以订阅多个子页面来发布、评论和互动。
Reddit 机器人是自动响应用户发帖或者每隔一定时间自动发帖的东西。这可能取决于用户发布的内容。它可以由某些关键短语触发，也取决于关于其内容的各种子循环。
为了实现一个 Reddit 机器人，我们将使用 Python Reddit API 包装器(PRAW)。它允许我们登录 Reddit API，直接与网站后端交互。关于这个库的更多信息可以在这里找到–[PRAW–Python Reddit API Wrapper](https://www.geeksforgeeks.org/python-praw-python-reddit-api-wrapper/)。

我们的机器人会告诉给定单词的相似单词。我们将使用`enchant`模块的`suggest()`方法来查找相似的单词。

**算法:**

1.  导入模块 praw 和附魔。
2.  使用有效参数创建授权的 Reddit 实例。
3.  选择机器人将居住的子边界。
4.  选择一个词来触发子循环中的机器人。
5.  检查子循环中的每个注释是否有触发短语。
6.  找到触发短语后，从评论中提取该词，并使用`enchant`模块找到其相似词。
7.  用类似的话回复评论。

```
# import the modules
import praw
import enchant

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

# the subreddit where the bot is to be live on
target_sub = "GRE"
subreddit = reddit.subreddit(target_sub)

# phrase to trigger the bot
trigger_phrase = "! GfGBot"

# enchant dictionary
d = enchant.Dict("en_US")

# check every comment in the subreddit
for comment in subreddit.stream.comments():

    # check the trigger_phrase in each comment
    if trigger_phrase in comment.body:

        # extract the word from the comment
        word = comment.body.replace(trigger_phrase, "")

        # initialize the reply text
        reply_text = ""

        # find the similar words
        similar_words = d.suggest(word)
        for similar in similar_words:
            reply_text += similar + " "

        # comment the similar words
        comment.reply(reply_text)
```

**触发机器人:**
![](img/5e7f7fee47d6bff50d1b755288bbdd0f.png)

**机器人用类似的话回复:**
![](img/ed6314a3151aa1268bfe5f23cd6c6ee2.png)