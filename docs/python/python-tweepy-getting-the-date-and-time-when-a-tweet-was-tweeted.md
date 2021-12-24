# Python Tweepy–获取推文发布的日期和时间

> 原文:[https://www . geeksforgeeks . org/python-tweepy-获取推文发布的日期和时间/](https://www.geeksforgeeks.org/python-tweepy-getting-the-date-and-time-when-a-tweet-was-tweeted/)

在本文中，我们将了解如何获取状态/推文发布/推文的日期和时间。Status 对象的 created_at 属性为我们提供了一个日期时间对象，它告诉我们状态是何时发布的。

**确定状态在图形用户界面中发布的日期:**
![](img/8db37840b7395c1000cbe84188847f80.png)

在上面提到的状态中，状态发布在:6 月 11 日

> 为了获得状态发布的日期和时间，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从该对象中，获取其中存在的 created_at 属性。

**例 1 :** 考虑以下状态:
![](img/b66484537992670523a54c9ba241fbc4.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272771459249844224。

```py
# import the module
import tweepy

# assign the values accordingly
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

# authorization of consumer key and consumer secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# set access to user's access key and access secret 
auth.set_access_token(access_token, access_token_secret)

# calling the api 
api = tweepy.API(auth)

# the ID of the status
id = 1272771459249844224

# fetching the status
user = api.get_status(id)

# fetching the created_at attribute
created_at = status.created_at 

print("The status was created at : " + str(created_at))
```

**输出:**

```py
The status was created at : 2020-06-16 06:02:17

```

**例 2 :** 考虑以下状态:
![](img/2893ea6f1652da3e4645b0bed573f047.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272479136133627905。

```py
# the ID of the status
id = 1272479136133627905

# fetching the status
user = api.get_status(id)

# fetching the created_at attribute
created_at = status.created_at 

print("The status was created at : " + str(created_at))
```

**输出:**

```py
The status was created at : 2020-06-15 10:40:42

```