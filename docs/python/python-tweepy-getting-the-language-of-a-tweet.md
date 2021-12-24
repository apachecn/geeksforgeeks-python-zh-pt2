# Python Tweepy–获取推文的语言

> 原文:[https://www . geeksforgeeks . org/python-tweepy-get-the-language-of-tweet/](https://www.geeksforgeeks.org/python-tweepy-getting-the-language-of-a-tweet/)

在本文中，我们将看到如何获取推文/状态的语言。Status 对象的 lang 属性表示状态的语言。语言在语言代码示例中表示，英语是 en，印地语是 hi。

> 为了获得语言的状态，我们必须做以下工作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。
> 3.  从这个对象中，获取其中存在的 lang 属性。

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

# fetching the lang attribute
lang = status.lang 

print("The language of the status is : " + lang)
```

**输出:**

```py
The language of the status is : en

```

**例 2 :** 考虑以下状态:
![](img/65875c98cedb182ca1cb57f8ed797462.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1273220141417816064。

```py
# the ID of the status
id = 1273220141417816064

# fetching the status
status = api.get_status(id)

# fetching the lang attribute
lang = status.lang 

print("The language of the status is : " + lang)
```

**输出:**

```py
The language of the status is : hi

```