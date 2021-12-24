# Python–在 Tweepy 中保存搜索对象

> 原文:[https://www . geesforgeks . org/python-savedsearch-object-in-tweepy/](https://www.geeksforgeeks.org/python-savedsearch-object-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## 保存搜索

Tweepy 模块中的 **`SavedSearch`** 对象包含有关已保存搜索的信息。

以下是保存的搜索对象中的属性列表:

> *   **id:** 保存的搜索的 id。
> *   **id _ str:** 保存的搜索的 id 是一个字符串。
> *   **查询:**搜索查询已保存。
> *   **名称:**保存的搜索的名称。
> *   **位置:**保存搜索的位置。
> *   **创建时间:**已保存搜索的创建时间。

**示例:**使用`get_saved_search()`方法获取保存的搜索。

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

# the ID of the saved search
id = 1272422627047378944

# fetching the saved search 
saved_search = api.get_saved_search(id)  

# printing the information
print("The id of the saved search is : " + str(saved_search.id))
print("The id_str of the saved search is : " + saved_search.id_str)
print("The query of the saved search is : " + saved_search.query)
print("The name of the saved search is : " + saved_search.name)
print("The position of the saved search is : " + str(saved_search.position))
print("The saved search was created at : " + str(saved_search.created_at))
```

**输出:**

```
The id of the saved search is : 1272422627047378944
The id_str of the saved search is : 1272422627047378944
The query of the saved search is : Tweepy
The name of the saved search is : Tweepy
The position of the saved search is : None
The saved search was created at : 2020-06-15 06:56:09

```