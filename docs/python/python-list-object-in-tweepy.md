# Python–Tweepy 中的列表对象

> 原文:[https://www.geeksforgeeks.org/python-list-object-in-tweepy/](https://www.geeksforgeeks.org/python-list-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 目录

Tweepy 模块中的**列表**对象包含关于列表的信息。
以下是列表对象中的属性列表:

> *   **id:** ID of the list.
> *   **id _ str:** The ID of the list is a string.
> *   **Name:** The name of the list.
> *   **uri:** the uri in the list.
> *   **Number of subscribers: the number of subscribers in the** list.
> *   **Member _ count:** Number of members in the list.
> *   **Mode:** The mode of the list.
> *   **slug: slug in the** list.
> *   **Full Name:** The full name of the list.
> *   **Creation time:** Creation time of the list.
> *   **is as follows:** indicates whether the authenticated user is following the list.
> *   **User:** The user object of the list owner.

**示例:**使用 get_list()方法获取列表。

## 蟒蛇 3

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

# the ID of the list
list_id = 4343

# fetching the list
list = api.get_list(list_id = list_id)

# printing the information
print("The id is : " + str(list.id))
print("The id_str is : " + list.id_str)
print("The name is : " + list.name)
print("The uri is : " + list.uri)
print("The subscriber_count is : " + str(list.subscriber_count))
print("The member_count is : " + str(list.member_count))
print("The mode is : " + list.mode)
print("The slug is : " + list.slug)
print("The full_name is : " + list.full_name)
print("The list was created on : " + str(list.created_at))
print("Is the authenticated user following the list? : " + str(list.following))
print("The screen name of the owner of the list is : " + list.user.screen_name)
```

**输出:**

```py
The id is : 4343
The id_str is : 4343
The name is : Thought Leaders
The uri is : /kitson/lists/thought-leaders
The subscriber_count is : 4066
The member_count is : 382
The mode is : public
The slug is : thought-leaders
The full_name is : @kitson/thought-leaders
The list was created on : 2009-10-15 23:03:44
Is the authenticated user following the list? : False
The screen name of the owner of the list is : kitson
```