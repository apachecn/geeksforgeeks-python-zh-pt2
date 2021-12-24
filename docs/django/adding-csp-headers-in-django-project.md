# 在姜戈项目中添加 CSP 头

> 原文:[https://www . geesforgeks . org/add-CSP-headers-in-django-project/](https://www.geeksforgeeks.org/adding-csp-headers-in-django-project/)

在开发网站和网络应用程序时，网站安全一直是一个重要因素。许多框架自带安全策略，开发人员在开发应用程序时也会尝试实施 atmost 安全策略。尽管如此，经过如此多的努力，黑客还是会找到新的方法渗透到我们的应用程序中，利用我们的代码漏洞。在本文中，我们将为 Django 应用程序实现一个通常称为 CSP 头的安全头。

#### 术语

*   **CSP**:Content-Security-Policy 是一个 HTTP 响应头，现代浏览器使用它来增强网页的安全性，它允许您限制 JavaScript、CSS 或浏览器加载的几乎任何资源的方式。
*   **HTTP 头** : HTTP 头让客户端和服务器通过 HTTP 请求或响应传递附加信息，如 MIME 类型、请求状态代码、cookie 和代理信息等
*   **XSS** :也缩写为 Cross Side Scripting，XSS 攻击使攻击者能够简单地将客户端脚本注入到其他用户查看的网页中，如果被利用，可以改变网页的外观和行为
*   **Django:** django 是一个基于 python 的 web 应用框架，用于构建各种 web 应用

#### 什么是内容安全策略？

**Content-Security-Policy i** 是一个 HTTP 响应头，现代浏览器使用它来增强网页的安全性，它允许您限制浏览器加载诸如 JavaScript、CSS 或几乎任何旨在防止 XSS 攻击的资源的方式，这些攻击使攻击者能够将客户端脚本注入到其他用户查看的网页中，简而言之，如果被利用，这些脚本可以改变网页的外观和行为。它也被称为 X-内容-安全-策略或 X-Webkit-CSP 头的后继。CSP 也可以使用元标签来实现。

一些 CSP 标题术语包括

*   default-src:加载所有内容的默认源
*   样式-src:加载样式的源
*   script-src:加载 javascript 或一般脚本的源代码
*   img-src:加载图像的来源
*   对象-src:加载媒体的源
*   报告到:uri，用于发送违反 CSP 的报告
*   ' self ':从同一主机加载
*   ' unsafe-inline ':允许内联样式和脚本
*   “unsafe-eval”:允许 eval()和类似的方法从字符串创建代码
*   nonce”:随机字符串，每个请求都应该是唯一的

#### 内容安全策略如何工作？

CSP 的工作原理是阻止样式、脚本和其他东西的执行，除非它们在策略中被允许。CSP 不允许执行内联脚本和样式，这意味着我们不能使用