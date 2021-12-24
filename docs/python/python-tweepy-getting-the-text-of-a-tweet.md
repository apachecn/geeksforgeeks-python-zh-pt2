# Python Tweepy–获取推文的文本

> 原文:[https://www . geesforgeks . org/python-tweepy-get-text-of-tweet/](https://www.geeksforgeeks.org/python-tweepy-getting-the-text-of-a-tweet/)

在本文中，我们将了解如何获取状态/推文的文本。一条推文最多只能有 280 个字符。状态对象的文本属性为我们提供了状态的文本。

**识别图形用户界面中状态的文本:**
![](img/f7c0cf54230c9dbf667cb4e4b7d44dbe.png)

在上述状态中，状态的文本为:

```
A programmer’s takeaway from the pandemic: Local variables over Global variables.

 What do you think?
.
.
.
.
.
#programming #coding  #programmingmemes #Covid_19 #codinglife #Python #javascript 
#pandemic #thursdayvibes

```

> 为了获得状态的文本，我们必须执行以下操作:
> 
> 1.  从图形用户界面识别状态的状态标识。
> 2.  使用带有状态标识的`get_status()`方法获取状态的状态对象。如果我们想得到完整的文本，传递另一个参数`tweet_mode = "extended"`。
> 3.  从该对象中，获取其中存在的文本属性。如果我们想获得完整的文本，获取属性 full_text。

**例 1 :** 考虑以下状态:
![](img/b66484537992670523a54c9ba241fbc4.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272771459249844224。

```
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

# fetching the text attribute
text = status.text 

print("The text of the status is : \n\n" + text)
```

**输出:**

```
The text of the status is : 

Which movie did you watch recently?

Reply us!
.
.
.
.
.
#tuesdaymood #TuesdayThoughts #Bollywood #Hollywood #genre 
#movies #movie #fun

```

**例 2 :** 考虑以下状态:
![](img/2893ea6f1652da3e4645b0bed573f047.png)

我们将使用状态标识来获取状态。上述状态的状态标识为 1272479136133627905。这次我们将获取状态的完整文本。使用`get_status()`方法时，也将`tweet_mode = "extended"`作为参数。然后使用 full_text 属性获取完整的文本。

```
# the ID of the status
id = 1272479136133627905

# fetching the status with extended tweet_mode
status = api.get_status(id, tweet_mode = "extended")

# fetching the full_text attribute
full_text = status.full_text 

print("The text of the status is : \n\n" + full_text)
```

**输出:**

```
The text of the status is : 

"I am thankful to programming for _______________."

Reply us most quirky/unexpected answers!
.
.
.
.
.
.
.
#coding #programming #codinglife #code #javascript #NodeJS  #reactjs #100DaysOfCode #codingisfun

```