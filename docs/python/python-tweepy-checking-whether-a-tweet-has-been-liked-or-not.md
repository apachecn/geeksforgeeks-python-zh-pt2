# Python Tweepy–检查一条推文是否被喜欢

> 原文:[https://www . geesforgeks . org/python-tweepy-checking-a-tweet-是否被喜欢过/](https://www.geeksforgeeks.org/python-tweepy-checking-whether-a-tweet-has-been-liked-or-not/)

在这篇文章中，我们将看到如何检查一条推文/状态是否被认证用户喜欢/偏爱。“状态”对象的“偏好”属性指示该状态是否已被经过身份验证的用户偏好。

**在 GUI 中识别身份验证用户是否喜欢该状态:**
![](img/a2cf04d996c91bb12e836a619db040f4.png)

在上面提到的状态中，心形图标是红色的，因此认证的用户喜欢这条推文。

> 为了检查身份验证用户是否喜欢该状态，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从该对象中，获取其中存在的偏好属性。

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
status = api.get_status(id)

# fetching the favorited attribute
favorited = status.favorited 

if favorited == True:
    print("The authenticated user has liked the tweet.")
else:
    print("The authenticated user has not liked the tweet.")
```

**输出:**

```py
The authenticated user has not liked the tweet.

```

**例 2 :** 考虑以下状态:
![](img/2893ea6f1652da3e4645b0bed573f047.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272479136133627905。

```py
# the ID of the status
id = 1272479136133627905

# fetching the status
status = api.get_status(id)

# fetching the favorited attribute
favorited = status.favorited 

if favorited == True:
    print("The authenticated user has liked the tweet.")
else:
    print("The authenticated user has not liked the tweet.")
```

**输出:**

```py
The authenticated user has liked the tweet.

```