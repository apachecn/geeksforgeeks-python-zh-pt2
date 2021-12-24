# 安全编码——它是关于什么的？

> 原文:[https://www . geesforgeks . org/secure-coding-what-it-all-about/](https://www.geeksforgeeks.org/secure-coding-what-is-it-all-about/)

你觉得你会编码吗？很高兴知道…这个世界肯定需要更多像你我这样的极客和书呆子…但是，**你的程序安全吗？**这就是整篇文章的主旨。

作为一名程序员，确保你的代码没有任何可能被其他黑帽黑客利用的空间，不仅是你的工作，也是你的道德责任。这就是 ***安全编码*** 的意义所在。如果你在谷歌上做一个关于安全编码的快速搜索，第一个会引起你注意的链接会是我们自己的 Wiki。

*安全编码是以防止安全漏洞意外引入的方式开发计算机软件的实践。缺陷、bug 和逻辑缺陷一直是经常被利用的软件漏洞的主要原因。*

好的。行话说够了……那到底是什么意思？我举个例子。现在，既然我是耍蛇人，我就用 Python 2.7x…

## 计算机编程语言

```
#test_run.py
pswd ="MY PASSWORD"
not_secret ="Geeks rock!"

inputVal = input("Please enter number of geeks") #A VERY BAD IDEA
print "There are", inputVal,"geeks here, chanting", not_secret
```

现在，继续试一试吧……它编译成功了，你知道吗，它给出了想要的输出！所以，这是我尝试不同输入时得到的……
**Run–1**
请输入极客数量 **5**

```
There are 5 geeks here, chanting Geeks rock!
```

**运行–2**
**请输入极客数量 **dir()**** 

```
There are **[‘pswd’, ‘not_secret’, ‘__builtins__’, ‘__doc__’, ‘__file__’,**
**‘__name__’, ‘__package__’]** geeks here, chanting **Geeks rock!**
```

****运行–3**
**请输入极客数量 **pswd****** 

```
**There are **MY PASSWORD** geeks here, chanting **Geeks rock!****
```

****如果你到现在还没有意识到，让我来陈述一下……这个程序运行得很完美！但是，不是以我们希望的方式……它打印出了我们的秘密数据……现在，你不能为此责怪语言，也不能责怪程序员……他/她做了他被要求做的事情……这就是**安全编码**发挥作用的地方。这个例子只是一个小例子，一个非常小的例子。开发一个程序有无数种可能性。你所需要的只是聪明的头脑和利用漏洞的经验。如果你是一个**网络安全**男/女，那么雇佣一个对安全编码标准一无所知或知之甚少的编码员可能是你可能犯的最大错误。因此，为了有一个安全的职业未来，有必要对安全编码标准有全面的了解。****

****现在，谁能决定什么是安全的编码方式？这不是一个程序员能做到的。谢天谢地，我们不需要为此烦恼。去看看 [**SEI CERT 编码标准**](https://www.securecoding.cert.org/confluence/display/seccode/SEI+CERT+Coding+Standards) 。它有一个非常好的建议步骤集合，以确保您的程序是安全的，并且根据编程语言进行排序——C、C++、Java、Perl 和 Android。但是，可悲的是，对于最简单的语言(在我看来)，没有给出这样的标准。这是否意味着 Python 程序总是安全的？不！！幸运的是，一些 Python 爱好者开始为 Python 列出类似的推荐列表，并导致了今天所知的 [**PEP 0008**](https://www.python.org/dev/peps/pep-0008/) 的诞生。它被称为 Python 代码的**风格指南**，创建于 2001 年。****

*****拥有一份“安全”和“不安全”程序的详尽列表，它是任何 Python 程序员的必备工具。*****

****现在，理论够了！让我们回到一些编码的东西！我现在要用一个高保真度的术语，你可以进一步用它来打动某人😉这个术语是**跨站点脚本(XSS)** 。在目前的情况下，每个网站都有一个评论区，允许访问者分享他们的经验，XSS 已经成为黑客经常使用的方法(不是一个好词！)窃取数据/发起分布式拒绝服务(DDOS)攻击/在客户端系统中安装病毒和恶意软件以及许多其他“不太好”的行为。****

****大多数注释部分允许用户用 HTML 代码编写，以提供格式化的机会。这意味着首先处理评论，然后在网站上打印结果。所以，假设我写了这样一段 JavaScript 代码，而不是注释:****

```
**window.alert(“Your comment has been received! – Geeks4Geeks”);**
```

****现在，按照我刚才讨论的，代码将被处理，客户端将收到一个弹出窗口，其中提到，“*您的评论已收到！–极客 4 eeks*。听起来不错……但是，想象一下可能性。一个人可以编写一个简单的脚本，在客户端系统中下载一个恶意软件/病毒，或者显示一个广告，该广告的内容会吸引他/她点击它，该广告将出现在一个可以窃取 cookies 的 IFrame 中(这被称为**点击劫持**)，这进一步导致了所谓的**会话劫持**；选项不限！那么，我们该怎么办呢？同样，解决方案在于安全编码！给你举个例子，如何避免 XSS，用姜戈点击劫持:****

```
**#**Clickjacking**

response = render_to_response(“webpage.html”, {},
context_instance=RequestContext(request))
response[‘X-Frame-Options’] = ‘DENY’ #Frame Killing
response[‘Content-Security-Policy’] = “frame-ancestors ‘none’”
return response**
```

****# **XSS**
#Django 默认情况下会转义 HTML，所以大多数程序都不会受到#XSS 攻击
* * { { contents } } * * #是安全的
* * { { contents | safe } } * * #覆盖转义，**不是个好主意****** 

****所以，基本上总结就是，如果你想在编码领域取得成功，那么就应该**养成遵守安全编码标准**的习惯。为什么呢？因为只有那些公众无法访问的程序才是安全的……一旦它们对所有人可用，就会有很多人试图破解你的代码……你最好小心点！****

****带着这个我告辞了！
**Auf wiedershen！** **！**(德语再见)
**关于作者:****** 

******维斯韦什·施里马里**是 BITS Pilani 的机械工程本科生。他符合****

****![vish](img/7f994f5cd1064d29bfe40308498171ec.png)****

****关于他的分支没有教过的所有要求——白帽黑客、网络安全操作员和前——竞争性程序员。作为 Python 力量的坚定信仰者，他的大部分作品都是同一种语言。每当他除了编程、上课、看 CSI Cyber 之外有时间的时候，他都会去散步，默默地弹吉他。他的人生格言是——“享受你的生活，因为它值得享受！”****

******如果你也想在这里展示你的博客，请查看**[**【GBlog】**](http://geeksquiz.com/gblog/)**在 GeeksforGeeks 上写客博。******