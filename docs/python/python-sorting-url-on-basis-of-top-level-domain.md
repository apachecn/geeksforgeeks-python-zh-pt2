# Python |基于顶级域的网址排序

> 原文:[https://www . geesforgeks . org/python-排序-基于顶级域的 URL/](https://www.geeksforgeeks.org/python-sorting-url-on-basis-of-top-level-domain/)

给定一个 URL 列表，任务是根据顶级域对列表中的 URL 进行排序。
A **顶级域名** (TLD)是互联网分级域名系统中级别最高的域名之一。示例–edu，org，com。
这主要用在我们必须报废页面并根据顶级域名对网址进行排序的情况下。它在开源项目中被广泛使用，并作为方便的代码片段使用。

```
Input :
url = ["https://www.isb.edu", "www.google.com", 
"http://cyware.com", "https://www.gst.in", 
"https://www.coursera.org", "https://www.create.net", 
"https://www.ontariocolleges.ca"]

Output :
['https://www.ontariocolleges.ca', 'www.google.com', 
'http://cyware.com', 'https://www.isb.edu', 
'https://www.gst.in', 'https://www.create.net',
 'https://www.coursera.org']

Explanation:
The Tld for the above list is in sorted order
['.ca','.com','.com','.edu','.in','.net','.org']

```

下面是一些完成上述任务的方法。

**方法一:使用排序后的**
可以拆分输入，然后使用排序按照 TLD 排序。

```
#Python code to sort the URL in the list based on the top-level domain.

#Url list initialization
Input = ["https://www.isb.edu", "www.google.com", "http://cyware.com",
 "https://www.gst.in", "https://www.coursera.org",
 "https://www.create.net", "https://www.ontariocolleges.ca"]

#Function to sort in tld order
def tld(Input):
    return Input.split('.')[-1]

#Using sorted and calling function
Output = sorted(Input,key=tld)

#Printing output
print("Initial list is :")
print(Input)
print("sorted list according to TLD is")
print(Output)
```

```
Initial list is :

['https://www.isb.edu', 'www.google.com', 'http://cyware.com',
 'https://www.gst.in', 'https://www.coursera.org', 
'https://www.create.net', 'https://www.ontariocolleges.ca']

Sorted list according to TLD is :

['https://www.ontariocolleges.ca', 'www.google.com', 
'http://cyware.com', 'https://www.isb.edu',
 'https://www.gst.in', 'https://www.create.net', 'https://www.coursera.org']

```

**方法二:使用 Lambda**
根据顶级域名对列表中的 URL 进行排序，最简洁易读的方法就是使用 Lambda。

```
#Python code to sort the URL in the list based on the top-level domain.

#Url list initialization
Input = ["https://www.isb.edu", "www.google.com", "http://cyware.com",
"https://www.gst.in", "https://www.coursera.org",
"https://www.create.net", "https://www.ontariocolleges.ca"]

#Using lambda and sorted 
Output = sorted(Input,key=lambda x: x.split('.')[-1])

#Printing output
print("Initial list is :")
print(Input)
print("sorted list according to TLD is")
print(Output)
```

```
Initial list is :

['https://www.isb.edu', 'www.google.com', 'http://cyware.com',
 'https://www.gst.in', 'https://www.coursera.org', 
'https://www.create.net', 'https://www.ontariocolleges.ca']

Sorted list according to TLD is :

['https://www.ontariocolleges.ca', 'www.google.com', 
'http://cyware.com', 'https://www.isb.edu',
 'https://www.gst.in', 'https://www.create.net', 'https://www.coursera.org']

```

**方法 3:使用反转**
反转输入并拆分，然后应用排序根据 TLD 对 URL 进行排序

```
#Python code to sort the URL in the list based on the top-level domain.

#Url list initialization
Input = ["https://www.isb.edu", "www.google.com", "http://cyware.com",
"https://www.gst.in", "https://www.coursera.org",
"https://www.create.net", "https://www.ontariocolleges.ca"]

#Internal function for reversed
def internal(string):
    return list(reversed(string.split('.')))

#Using sorted and calling internal for reversed
Output = sorted(Input, key=internal)

#Printing output
print("Initial list is :")
print(Input)
print("sorted list according to TLD is")
print(Output)
```

```
Initial list is :

['https://www.isb.edu', 'www.google.com', 'http://cyware.com',
 'https://www.gst.in', 'https://www.coursera.org', 
'https://www.create.net', 'https://www.ontariocolleges.ca']

Sorted list according to TLD is :

['https://www.ontariocolleges.ca', 'www.google.com', 
'http://cyware.com', 'https://www.isb.edu',
 'https://www.gst.in', 'https://www.create.net', 'https://www.coursera.org']

```