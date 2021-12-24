# Python–Tweepy 中的状态对象

> 原文:[https://www . geesforgeks . org/python-status-object-in-tweepy/](https://www.geeksforgeeks.org/python-status-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 状态

Tweepy 模块中的 **`Status`** 对象包含关于状态/推文的信息。

以下是状态对象中的属性列表:

> *   **Creation time:** The time when the status was published.
> *   **id: ID of** status.
> *   **id _ str:** ID with string status.
> *   **Text: Text in** state.
> *   **Entity: the analytic entity of** status, such as label, website, etc.
> 
> **来源:**
> 
> *   **Source _ url:** The URL of the status source.
> *   **in _ reply _ to _ status _ id:** 被回复状态的身份证.
> *   **In _ reply _ to _ status _ ID _ str:** As the ID of the status to which the string is replied.
> *   **in _ reply _ to _ user _ id:** 被回复用户的身份证.
> *   [T0】 in _ reply _ to _ user _ id _ str: 【T1] The ID of the user who replied as a string.
> *   [T0】 in _ reply _ to _ screen _ name: 【T1] The screen name of the user to whom the reply is made.
> *   **User:** The user object of the status poster.
> *   **Geography:** The status of geographical objects.
> *   **Coordinate: the coordinate of** state.
> *   **Place:** The place of status.
> *   **Contributor:** The status of the contributor.
> *   **is _ quote _ status:** indicates whether the status is quotation status.
> *   **forwarding times _ count: forwarding times in** state.
> *   **Favorite _ count:** Number of likes in the state.
> *   **Preference:** indicates whether the status has been authenticated or not.
> *   **Forwarding:** indicates whether the status has been forwarded by the authenticated user.
> *   **Possible _ Sensitive:** indicates whether the state is sensitive or not.
> *   **Lang:** The language of status.

**例:**考虑以下状态:
![](img/05949214eb274fd1f0cab6fbb5f6f7b5.png)
使用`get_status()`方法获取状态。

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
id = 1268080321590935553

# fetching the status
status = api.get_status(id)

# printing the information
print("The status was created at : " + str(status.created_at))
print("The id is : " + str(status.id))
print("The id_str is : " + status.id_str)
print("The text is : " + status.text)
print("The entitities are : " + str(status.entities))
print("The source is : " + status.source)
print("The source_url is : " + status.source_url)

print("The in_reply_to_status_id is : " + str(status.in_reply_to_status_id))
print("The in_reply_to_status_id_str is : " + str(status.in_reply_to_status_id_str))
print("The in_reply_to_user_id is : " + str(status.in_reply_to_user_id))
print("The in_reply_to_user_id_str is : " + str(status.in_reply_to_user_id_str))
print("The in_reply_to_screen_name is : " + str(status.in_reply_to_screen_name))

print("The poster's screen name is : " + status.user.screen_name)
print("The geo is : " + str(status.geo))
print("The coordinates are : " + str(status.coordinates))
print("The place is : " + str(status.place))
print("The contributors are : " + str(status.contributors))
print("The is_quote_status is : " + str(status.is_quote_status))
print("The retweet_count is : " + str(status.retweet_count))
print("The favorite_count is : " + str(status.favorite_count))

print("Has the authenticated user favourited the status? : " + str(status.favorited))
print("Has the authenticated user retweeted the status? " + str(status.retweeted))
print("Is the status possibly_sensitive? : " + str(status.possibly_sensitive))
print("The lang is : " + status.lang)
```

**输出:**

> 状态创建于:2020-06-03 07:21:23
> id 为:1268080321590935553
> id _ str 为:1268080321590935553
> 文字为:当你是
> 的时候，时间真的打得不一样吗？？
> 拿着木板一分钟？？洗手 20 秒，然后…https://t.co/BBg2RIamGy
> 实体有:{'hashtags': []，' symbols': []，' user _ references ':[]，' URL ':[{ ' URL ':' https://t . co/BBg2RIamGy '，' expanded _ URL ':' https://Twitter . com/I/web/status/1268080321590935553 '，' display _ URL ':' Twitter . com/I/web/status/1…'，' indexs ':[2] 139]}]}
> 来源为:Twitter Web App
> 来源 _url 为:https://mobile.twitter.com
> in _ reply _ to _ status _ id 为:None
> in _ reply _ to _ status _ id _ str 为:None
> in _ reply _ to _ user _ id 为:None
> in _ reply _ to _ user _ id _ str 为:None
> in _ reply _ to _ screen _ name 为:None
> 海报的网名 :False
> 转发次数为:2
> 收藏次数为:31
> 认证用户是否喜欢该状态？ :真
> 认证用户转发状态了吗？假
> 状态可能 _ 敏感吗？:假
> 郎是:恩