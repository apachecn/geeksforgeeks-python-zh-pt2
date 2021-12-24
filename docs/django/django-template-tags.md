# 姜戈模板标记

> 哎哎哎:# t0]https://www . geeksforgeeks . org/django-template tags/

Django Web Framework 附带了几十个标签，用于在模板中实现任意逻辑。标签看起来像这样:`{% tag %}`。标签比变量更复杂:有些标签在输出中创建文本，有些标签通过执行循环或逻辑来控制流程，有些标签将外部信息加载到模板中供后面的变量使用。标签在渲染过程中提供任意逻辑。例如，标签可以输出内容，用作控制结构，例如“if”语句或“For”循环，从数据库中抓取内容，甚至允许访问其他模板标签。

###### 句法

```
{% tag_name %}
```

###### 例子

标签由{%和%}包围，如下所示:

```
{% csrf_token %}
```

大多数标签接受参数，例如:

```
{% cycle 'odd' 'even' %}
```

## Django 模板中常用的标签

1.  #### 评论

    模板会忽略{% comment %}和{% endcomment %}之间的所有内容。可以在第一个标签中插入可选的注释。例如，这在注释代码以记录代码被禁用的原因时非常有用。
    **例**

    ```
    {% comment "Optional note" %}

    Commented out text with {{ create_date|date:"c" }}

    {% endcomment %}

    ```

    要查看更多关于评论标签的信息，请访问–[评论–姜戈模板标签](https://www.geeksforgeeks.org/comment-django-template-tags/)

2.  #### 循环

    每次遇到这个标记时，它都会生成一个参数。第一个论点产生于第一次相遇，第二个论点产生于第二次相遇，依此类推。一旦所有的参数都用完了，标签就会循环到第一个参数并再次生成它。
    **示例**
    这个标签在循环中特别有用:

    ```
    {% for o in some_list %} 
        <tr class="{% cycle 'row1' 'row2' %}"> 
            ... 
        </tr> 
    {% endfor %} 
    ```

    对于循环的每次迭代，第一次迭代生成引用类行 1 的 HTML，第二次迭代生成行 2，第三次迭代再次生成行 1，依此类推。
    要查看更多关于周期标签的信息，请访问–[周期–](https://www.geeksforgeeks.org/cycle-django-template-tags/)姜戈模板标签

3.  #### 延伸

    extends 标签用于 django 中模板的继承。人们需要一遍又一遍地重复同样的代码。使用扩展，我们可以继承模板和变量。
    **例**
    假设如下目录结构:

    ```
    dir1/
        template.html
        base2.html
        my/
            base3.html
    base1.html
    ```

    在 template.html，以下路径是有效的:

    ```
    {% extends "./base2.html" %}
    {% extends "../base1.html" %}
    {% extends "./my/base3.html" %}
    ```

    要查看更多关于扩展标签的信息，请访问–[扩展–姜戈模板标签
    T2](https://www.geeksforgeeks.org/extends-django-template-tags/)

4.  #### 如果

    {% if %}标记计算一个变量，如果该变量为“真”(即存在，不为空，并且不是假布尔值)，则输出块的内容。**例**

    ```
    {% if athlete_list %}
        Number of athletes: {{ athlete_list|length }}
    {% elif athlete_in_locker_room_list %}
        Athletes should be out of the locker room soon!
    {% else %}
        No athletes.
    {% endif %}
    ```

    在上图中，如果运动员列表不为空，运动员的数量将由`{{ athlete_list|length }}`变量显示。

    可以看到，if 标签可能包含一个或多个`{% elif %}`子句，以及一个`{% else %}`子句，如果前面所有条件都失败，该子句将被显示。这些条款是可选的。

    要查看更多关于 if 标签的信息，请访问–[if–姜戈模板标签](https://www.geeksforgeeks.org/if-django-template-tags/) 

5.  #### for 循环

    for tag 循环遍历数组中的每一项，使该项在上下文变量中可用。
    **示例**
    例如，要显示运动员列表中提供的运动员列表:

    ```
    <ul>
    {% for athlete in athlete_list %}
        <li>{{ athlete.name }}</li>
    {% endfor %}
    </ul>
    ```

    要查看有关循环标签的更多信息，请访问–[了解循环–【姜戈模板标签】
    T2](https://www.geeksforgeeks.org/for-loop-django-template-tags/)

6.  #### for …空循环

    for tag 循环遍历数组中的每一项，使该项在上下文变量中可用。for 标记可以采用可选的`{% empty %}`子句，如果给定的数组为空或找不到，则显示该子句的文本。这基本上是用来作为一个条件来检查 queryset 是否为空，以及在相同的场景中要执行什么操作。

    **例**

    ```
    <ul> 
    {% if athlete_list %} 
        {% for athlete in athlete_list %} 
        <li>{{ athlete.name }}</li> 
        {% endfor %} 
    {% else %} 
        <li>Sorry, no athletes in this list.</li> 
    {% endif %} 
    </ul> 
    ```

    要查看更多关于…空循环标签的信息，请访问–[查看…空循环–
    姜戈模板标签](https://www.geeksforgeeks.org/for-empty-loop-django-template-tags/)

7.  #### 布尔运算符

    `{% if %}`标记计算一个变量，如果该变量为“真”(即存在，不为空，并且不是假布尔值)，则输出该块的内容。人们可以在 Django If 模板标签中使用各种布尔运算符。

    **例**

    ```
    <ul> 
    {% if variable boolean_operator value %}
    // statements
    {% endif %}
    </ul> 
    ```

    要查看关于布尔运算符的更多信息，请访问–[布尔运算符–](https://geeksforgeeks.org/boolean-operators-django-template-tags/)姜戈模板标签

8.  #### 第一

    firstof 标记输出不是“假”的第一个参数变量(即存在，不是空的，不是假的布尔值，也不是零数值)。如果所有传递的变量都为“假”，则不输出任何内容。

    **例**

    ```
    {% firstof var1 var2 var3 %}
    ```

    这相当于:

    ```
    {% if var1 %}
        {{ var1 }}
    {% elif var2 %}
        {{ var2 }}
    {% elif var3 %}
        {{ var3 }}
    {% endif %}
    ```

    如果所有传递的变量都为 False，也可以使用文字字符串作为后备值:

    ```
    {% firstof var1 var2 var3 "fallback value" %}
    ```

    要查看更多关于第一标签的信息，请访问–[第一标签–姜戈模板标签](https://geeksforgeeks.org/firstof-django-template-tags/) 

9.  #### 包括

    include 标记加载一个模板，并用当前上下文呈现它。这是一种在模板中“包含”其他模板的方式。模板名称可以是变量，也可以是硬编码(带引号)的字符串，可以是单引号或双引号。

    **例**

    ```
    {% include "foo/bar.html" %}
    ```

    通常模板名称是相对于模板加载器的根目录的。字符串参数也可以是以。/或../如[中所述扩展](https://docs.djangoproject.com/en/3.0/ref/templates/builtins/#extends)标签。

    要查看更多关于包含标签的信息，请访问–[包含–姜戈模板标签](https://geeksforgeeks.org/include-django-template-tags/) 

10.  #### 洛伦

    lorem 标签显示随机的“lorem ipsum”拉丁文本。这对于在模板中提供示例数据非常有用。

    **例**

    *   {% lorem %}将输出常见的“lorem ipsum”段落。
    *   {% lorem 3 p %}将输出常见的“lorem ipsum”段落和两个随机段落，每个段落都用 HTML 标记包装。
    *   {% lorem 2 w random %}将输出两个随机拉丁单词。

    要查看更多关于 lorem 标签的信息，请访问–[lorem–姜戈模板标签](https://www.geeksforgeeks.org/lorem-django-template-tags/) 

11.  #### 现在

    现在标签显示当前日期和/或时间，使用根据给定字符串的格式。这种字符串可以包含格式说明符字符，如[日期过滤器](https://docs.djangoproject.com/en/3.0/ref/templates/builtins/#std:templatefilter-date)部分所述。
    **例**

    ```
    It is {% now "D d M Y" %}
    ```

    上述标签将于 2020 年 2 月 4 日星期二显示

    要查看更多关于 now 标签的信息，请访问–[now–姜戈模板标签](https://www.geeksforgeeks.org/now-django-template-tags/) 

12.  #### 全球资源定位器(Uniform Resource Locator)

    url 标记返回与给定视图和可选参数匹配的绝对路径引用(不带域名的 URL)。这是一种不违反 DRY 原则的输出链接的方法，因为你必须在模板中硬编码网址。
    **例**

    ```
    {% url 'some-url-name' v1 v2 %}
    ```

    第一个参数是一个网址模式名。它可以是带引号的文字或任何其他上下文变量。附加参数是可选的，并且应该是将在 URL 中用作参数的空格分隔的值。

    要查看更多关于网址标签的信息，请访问–[网址–姜戈模板标签](https://www.geeksforgeeks.org/url-django-template-tags/)