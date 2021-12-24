# 使用美丽组合导航

> 原文:[https://www . geesforgeks . org/navigation-with-beautulsoup/](https://www.geeksforgeeks.org/navigation-with-beautifulsoup/)

[**【美化组】**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/) 是一个用于解析 HTML 和 XML 文档的 Python 包，它为解析的 paged 创建一个解析树，可用于网页抓取，它从 HTML 和 XML 文件中提取数据，并与您最喜欢的解析器一起工作，提供导航、搜索和修改解析树的惯用方式。

### **安装**

这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```
pip install bs4
```

### **带漂亮组件的导航**

下面的代码片段是我们将使用的 HTML 文档，以此代码片段作为参考，使用美丽的输出标签进行导航。

## 蟒蛇 3

```
ht_doc = """

<html><head><title>Geeks For Geeks</title></head>

<body>

<p class="title"><b>most viewed courses in GFG,its all free</b></p>

<p class ="prog">Top 5 Popular Programming Languages</p>

<a href="https://www.geeksforgeeks.org/java-programming-examples/" \
class="prog" id="link1">Java</a>
<a href="https://www.geeksforgeeks.org/cc-programs/" class="prog" \
id="link2">c/c++</a>
<a href="https://www.geeksforgeeks.org/python-programming-examples/"\
class="prog" id="link3">Python</a>
<a href="https://https://www.geeksforgeeks.org/introduction-to-javascript/"\
class="prog" id="link4">Javascript</a>
<a href="https://www.geeksforgeeks.org/ruby-programming-language/" \
class="prog" id="link5">Ruby</a>

<p>according to an online survey. </p>

<p class="prog"> Programming Languages</p>

</body></html>

"""
```

现在，让我们通过在上面的代码片段上应用 Python 中的 BeautifulSoup，以所有可能的方式进行导航，Html 文档中最重要的组件是标签，这些标签也可能包含其他标签/字符串(标签的子级)。美化组提供了不同的方法来迭代这些孩子，让我们看到所有可能的情况

### **向下导航**

#### **使用标签名称导航:**

**例 1:** 获取头牌。

使用。head to BeautifulSoup 对象获取 HTML 文档中的 head 标签。

> **语法:**(美化输出变量)。头

**示例 2:** 获取标题标签

使用。标题标签，用于检索嵌入在美化输出变量中的 HTML 文档的标题

> **语法:**(美化输出变量)。标题

**代码:**

## 蟒蛇 3

```
soup = BeautifulSoup(ht_doc, 'html.parser')
print(soup.head)
print(soup.title)
```

**输出:**

```
<head><title>Geeks For Geeks</title></head>
<title>Geeks For Geeks</title>
```

**示例 3:** 获取特定标签。

我们可以检索一些特定的标签，比如主体标签中的第一个**标签**

> **语法:**(美化输出变量)

使用标签名作为属性将获得该名称的名字

> **语法:**(美化输出变量)。(标签属性)

通过使用 find_all，我们可以获得与该属性相关联的所有内容

> **语法:**(美化输出变量)。find_all(标记值)

**代码:**

## 蟒蛇 3

```
soup = BeautifulSoup(ht_doc, 'html.parser')

# retrieving b tag element
print(soup.body.b)

# retrieving a tag leement from BeautifulSoup assigned variable
print(soup.a)

# retrieving all elements tagged with a in ht_doc
print(soup.find_all("a"))
```

**输出:**

> **GFG 观看人数最多的课程，全部免费**
> 
> [Java](”https://www.geeksforgeeks.org/java-programming-examples/”)
> 
> 【 [Java](”https://www.geeksforgeeks.org/java-programming-examples/”) 、
> 
> [c/c++](”https://www.geeksforgeeks.org/cc-programs/”) ，
> 
> [蟒蛇](”https://www.geeksforgeeks.org/python-programming-examples/”)，
> 
> [Javascript](”https://https://www.geeksforgeeks.org/introduction-to-javascript/”) ，
> 
> [红宝石](”https://www.geeksforgeeks.org/ruby-programming-language/”)

**实施例 4:** 内容和。儿童

我们可以通过使用. contents 在列表中获取标签子级。

> **语法:**(美化输出变量)。内容

**代码:**

## 蟒蛇 3

```
soup = BeautifulSoup(ht_doc, 'html.parser')

# assigning head tag of BeautifulSoup variable
hTag = soup.head
print(hTag)

# retrieving contents of BeautifulSoup variable
print(hTag.contents)
```

**输出:**

```
<head><title>Geeks For Geeks</title></head>
[<title>Geeks For Geeks</title>]
```

**例 5:** 。后代

那个。后代属性允许您递归地迭代一个标签的所有子标签——它的直接子标签和它的直接子标签的子标签，等等…

> **语法:**(从美化组变量分配的变量)。后代

**代码:**

## 蟒蛇 3

```
# embedding html document inyto BeautifulSoup variable
soup = BeautifulSoup(ht_doc, 'html.parser')

# assigning head element of BeautifulSoup-assigned Variable
htag=soup.head

# iterating through child in descendants of htag variable
for child in htag.descendants:
    print(child)
```

**输出:**

```
<title>Geeks For Geeks</title>
Geeks For Geeks
```

**例 6:** 。线

如果标签只有一个子标签，并且该子标签是 NavigableString，则该子标签可以作为。线

然而，如果一个标签包含不止一个东西，那么不清楚是什么。字符串应该引用，所以。字符串被定义为无，我们可以在下面的代码中看到这种实用的工作方式。

## 蟒蛇 3

```
soup = BeautifulSoup(ht_doc, 'html.parser')
htag = soup.head
print(htag.string)
```

**输出:**

```
Geeks For Geeks
```

**例 7:。字符串和剥离 _ 字符串**

如果标签中有不止一个东西，您仍然可以只查看字符串。使用。字符串生成器。

## 蟒蛇 3

```
soup = BeautifulSoup(ht_doc, 'html.parser')
for string in soup.strings :
    print(repr(string))
```