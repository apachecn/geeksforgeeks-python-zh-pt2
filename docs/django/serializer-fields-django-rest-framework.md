# 序列化程序字段–姜戈 REST 框架

> 原文:[https://www . geesforgeks . org/serializer-fields-django-rest-framework/](https://www.geeksforgeeks.org/serializer-fields-django-rest-framework/)

在 Django REST 框架中，序列化程序附带一些字段(条目)，用于处理序列化程序中的数据。序列化的真正动机是将数据库数据转换为 javascript 可以使用的数据类型。例如，如果您有一个名为 Employee 的类，其字段为 Employee_id、Employee_name、is_admin 等。然后，您将需要自动字段、字符字段和 BooleanField 来通过 Django 存储和操作数据。我们需要多个字段来对数据进行默认验证，也就是说，我们将使用 EmailField 来存储电子邮件，因为它将数据验证到电子邮件地址。
本文围绕 Django REST 框架中的序列化程序中可以使用的多个字段以及如何使用这些字段展开。Django REST 框架中的序列化程序字段可以分为以下几类–

*   [布尔字段](#boolean-fields)
*   [字符串字段](#string-fields)
*   [数值字段](#numeric-fields)
*   [日期和时间字段](#date-time-fields)
*   [选择选择字段](#choice-selection-fields)
*   [文件上传字段](#file-upload-fields)
*   [串行器字段](#serializer-fields)
*   [序列化程序字段中的核心参数](#core-arguments)

### 布尔字段

布尔型字段有两个主要字段——布尔型字段和布尔型字段。

#### BooleanField

用于包装**真**或**假**值的布尔字段。其工作原理与[BooleanField-Django 车型](https://www.geeksforgeeks.org/booleanfield-django-models/)相同。默认情况下，序列化程序。默认情况下创建的 BooleanField 实例为 False。
**语法–**

```
field_name = serializers.BooleanField() 
```

#### NullBooleanField

接受**真**、**假**和**空**值的布尔字段。其工作原理与[NullBooleanField–Django 模型](https://www.geeksforgeeks.org/nullbooleanfield-django-forms/)相同。默认情况下，序列化程序。默认情况下，创建的 NullBooleanField 实例为无。
**语法–**

```
field_name = serializers.NullBooleanField()
```

要查看更多信息，请访问–[序列化程序中的布尔字段–](https://www.geeksforgeeks.org/boolean-fields-in-serializers-django-rest-framework/)

### 字符串字段

有三个主要字段——字符字段、电子邮件字段和正则表达式字段。

#### carfield

CharField 用于存储文本表示。(可选)验证文本是否短于 max_length 且长于 min_length。其工作原理与[CharField-Django 模型](https://www.geeksforgeeks.org/charfield-django-models/)相同。
它有以下论点

*   **最大长度**–验证输入包含的字符不超过此数量。
*   **min _ length**–验证输入包含不少于此数量的字符。
*   **允许 _ 空白**–如果设置为真，则空字符串应被视为有效值。如果设置为假，则空字符串被视为无效，并将引发验证错误。默认为假。
*   **修剪空白**–如果设置为真，则修剪前导和尾随空白。默认为真。

**语法–**

```
field_name = serializers.CharField(*args, **kwargs) 
```

#### 电子邮件字段

EmailField 也是一种文本表示，它验证文本是有效的电子邮件地址。与[EmailField–Django Models](https://www.geeksforgeeks.org/emailfield-django-models/)相同。对于相同的功能，它接受 CharField 的所有参数。
**语法–**

```
field_name = serializers.EmailField(*args, **kwargs) 
```

#### RegexField

正如名称所定义的，RegexField 将字符串与特定的 regex 匹配，否则会引发错误。与[regex field–Django 表单](https://www.geeksforgeeks.org/regexfield-django-forms/)相同。对于相同的功能，它接受 CharField 的所有参数。
**语法–**

```
field_name = serializers.RegexField(*args, **kwargs)
```

要查看更多信息，请访问–[序列化程序中的字符串字段–](https://www.geeksforgeeks.org/string-fields-in-serializers-django-rest-framework/)

### 网址字段

有两个主要字段——URL field 和 SlugField。

#### URLField 先生

URLField 基本上是一个正则表达式字段，它根据 URL 匹配模式验证输入。需要 http:///形式的完全限定的 URL。其工作原理与[乌尔菲尔德-姜戈模型](https://www.geeksforgeeks.org/urlfield-django-models/)相同

它有以下参数–

*   **允许 _ 空白**–如果设置为真，则空字符串应被视为有效值。如果设置为假，则空字符串被视为无效，并将引发验证错误。默认为假。

**语法–**

```
field_name = serializers.URLField(*args, **kwargs) 
```

#### 斯拉格菲尔德

SlugField 是一个 RegexField，它根据模式[a-zA-Z0-9_-]+，验证输入。与[斯拉格菲尔德-姜戈车型](https://www.geeksforgeeks.org/slugfield-django-models/)相同。

**语法–**

```
field_name = serializers.SlugField(*args, **kwargs)
```

要查看更多信息，请访问序列化程序-姜戈 REST 框架中的–[网址字段](https://www.geeksforgeeks.org/url-fields-in-serializers-django-rest-framework/)

### 数字字段

有三个主要字段——整数字段、浮点字段和十进制字段。

#### -你是什么意思

IntegerField 基本上是一个整数字段，它根据 Python 的 **int** 实例验证输入。与[IntegerField-Django 车型](https://www.geeksforgeeks.org/integerfield-django-models/)相同

它有以下参数–

*   **最大值**验证提供的数值不大于该值。
*   **min_value** 验证提供的数字不小于该值。

**语法–**

```
field_name = serializers.IntegerField(*args, **kwargs) 
```

#### 浮动字段

FloatField 基本上是一个浮动字段，它根据 Python 的 **float** 实例来验证输入。与[浮动场-姜戈模型](https://www.geeksforgeeks.org/floatfield-django-models/)相同

它有以下参数–

*   **最大值**验证提供的数值不大于该值。
*   **min_value** 验证提供的数字不小于该值。

**语法–**

```
field_name = serializers.FloatField(*args, **kwargs) 
```

#### 十进制字段

十进制字段基本上是一个十进制字段，根据 Python 的**十进制**实例验证输入。与[德米拉尔菲尔德-姜戈车型](https://www.geeksforgeeks.org/decimalfield-django-models/)相同

它有以下参数–

*   **最大位数**数字中允许的最大位数。它必须是无或大于或等于小数位数的整数。
*   **小数位数**与数字一起存储的小数位数。
*   **最大值**验证提供的数值不大于该值。
*   **min_value** 验证提供的数字不小于该值。
*   **本地化**设置为真，根据当前区域设置启用输入和输出的本地化。

**语法–**

```
field_name = serializers.DecimalField(*args, **kwargs)
```

要查看更多信息，请访问–[序列化程序中的数值字段–【Django REST 框架】](https://www.geeksforgeeks.org/numeric-fields-in-serializers-django-rest-framework/#integerfield)

### 日期和时间字段

有四个主要字段–日期时间字段、日期字段、时间字段和工期字段。

#### 日期时间字段

DateTimeField 是用于日期和时间表示的序列化程序字段。与–[日期时间字段–姜戈模型](https://www.geeksforgeeks.org/datetimefield-django-models/)相同

它有以下参数–

*   **格式**–表示输出格式的字符串。如果未指定，这将默认为与 DATETIME_FORMAT 设置键相同的值，除非设置为“iso-8601”。设置为格式字符串表示 to _ expression 返回值应该强制为字符串输出。格式字符串描述如下。将该值设置为“无”表示 Python 日期时间对象应该由 to _ representation 返回。在这种情况下，日期时间编码将由渲染器决定。
*   **输入格式**–表示可用于解析日期的输入格式的字符串列表。如果未指定，将使用 DATETIME_INPUT_FORMATS 设置，默认为['iso-8601']。
*   **default _ time zone**–表示时区的 pytz.timezone。如果未指定并且启用了“使用 TZ”设置，则默认为当前时区。如果禁用了 USE_TZ，那么日期时间对象将是幼稚的。

**语法–**

```
field_name = serializers.DateTimeField(*args, **kwargs) 
```

#### 戴达菲尔德

日期字段是用于日期表示的序列化程序字段。通常，人们需要存储日期，例如在博客模型中，每个帖子的日期都需要存储。该字段与[日期字段相同–姜戈模型](https://www.geeksforgeeks.org/datefield-django-models/)
它有以下参数–

*   **格式**–表示输出格式的字符串。如果未指定，这将默认为与 DATE_FORMAT 设置键相同的值，除非设置为“iso-8601”。设置为格式字符串表示 to _ expression 返回值应该强制为字符串输出。格式字符串描述如下。将该值设置为“无”表示 Python 日期对象应该由 to _ representation 返回。在这种情况下，日期编码将由渲染器决定。
*   **输入格式**–表示可用于解析日期的输入格式的字符串列表。如果未指定，将使用 DATE _ INPUT _ FORMATS 设置，默认为['iso-8601']。

**语法–**

```
field_name = serializers.DateField(*args, **kwargs) 
```

#### 时间字段

Timefield 是用于时间表示的序列化程序字段。通常，人们需要存储日期，例如在博客模型中，每个帖子的时间都需要存储。

它有以下参数–

*   **格式**–表示输出格式的字符串。如果未指定，这将默认为与 TIME_FORMAT 设置键相同的值，除非设置为“iso-8601”。设置为格式字符串表示 to _ expression 返回值应该强制为字符串输出。格式字符串描述如下。将该值设置为“无”表示 Python 时间对象应该由 to _ representation 返回。在这种情况下，时间编码将由渲染器决定。
*   **输入格式**–表示可用于解析日期的输入格式的字符串列表。如果未指定，将使用时间 _ 输入 _ 格式设置，默认为['iso-8601']。

**语法–**

```
field_name = serializers.TimeField(*args, **kwargs) 
```

#### 工期字段

持续时间字段是用于持续时间表示的序列化程序字段。该字段与[持续时间字段相同–姜戈模型](https://www.geeksforgeeks.org/durationfield-django-models/)
它有以下参数–

*   **最大值**验证提供的持续时间不大于该值。
*   **min_value** 验证提供的持续时间不小于该值。

**语法–**

```
field_name = serializers.DurationField(*args, **kwargs)
```

要查看更多信息，请访问–[序列化程序中的日期和时间字段–](https://www.geeksforgeeks.org/date-and-time-fields-in-serializers-django-rest-framework/)

### 选项选择字段

有两个主要字段–选择和多重处理字段。

#### 选择字段

ChoiceField 基本上是一个字符域，它根据一组有限选项中的一个值来验证输入。该字段与[选择字段-姜戈表单](https://www.geeksforgeeks.org/choicefield-django-forms/)相同。

它有以下参数–

*   **选项**–有效值列表，或(键，display_name)元组列表。
*   **允许 _ 空白**–如果设置为真，则空字符串应被视为有效值。如果设置为假，则空字符串被视为无效，并将引发验证错误。默认为假。
*   **html _ cutting**–如果设置，这将是 HTML 选择下拉菜单显示的最大选项数。可用于确保自动生成的选项字段具有非常大的可能选择，不会阻止模板呈现。默认为无。
*   **html _ cut _ text**–如果设置，如果 HTML 选择下拉列表中的最大项目数已被截断，将显示一个文本指示器。默认为“超过{计数}个项目…”

**语法–**

```
field_name = serializers.ChoiceField(*args, **kwargs) 
```

#### 多选择字段

ChoiceField 基本上是一个字符域，它根据从一组有限的选项中选择的一组零个、一个或多个值来验证输入。该字段与[多选择字段-姜戈表单](https://www.geeksforgeeks.org/multiplechoicefield-django-forms/)相同。

**语法–**

```
field_name = serializers.MultipleChoiceField(*args, **kwargs)
```

要查看更多信息，请访问–[序列化程序中的选择字段–【姜戈 REST 框架】](https://www.geeksforgeeks.org/choice-selection-fields-in-serializers-django-rest-framework/#choicefield)

### 文件上传字段

有两个主要字段—文件字段和图像字段。

#### 文件字段

FileField 基本上是一种文件表示。它执行 Django 的标准文件字段验证。该字段与[文件字段-姜戈模型](https://www.geeksforgeeks.org/filefield-django-models/)相同。

它有以下参数–

*   **最大长度**–指定文件名的最大长度。
*   **允许空文件**–指定是否允许空文件。
*   **使用 _ url**–如果设置为真，则 URL 字符串值将用于输出表示。如果设置为假，文件名字符串值将用于输出表示。默认为上传文件使用网址设置键的值，除非另有设置，否则为真。

**语法–**

```
field_name = serializers.FileField(*args, **kwargs) 
```

#### ImageField(图像字段)

ImageField 是一种图像表示。它验证上传的文件内容是否与已知的图像格式相匹配。这与[ImageField–Django 表单](https://www.geeksforgeeks.org/imagefield-django-forms/)相同

它有以下参数–

*   **最大长度**–指定文件名的最大长度。
*   **允许空文件**–指定是否允许空文件。
*   **使用 _ url**–如果设置为真，则 URL 字符串值将用于输出表示。如果设置为假，文件名字符串值将用于输出表示。默认为上传文件使用网址设置键的值，除非另有设置，否则为真。

**语法–**

```
field_name = serializers.ImageField(*args, **kwargs)
```

要查看更多信息，请访问–[序列化程序中的文件上传字段–姜戈 REST 框架](https://www.geeksforgeeks.org/file-upload-fields-in-serializers-django-rest-framework/)

## 序列化字段

。数学表{边框折叠:折叠；宽度:100%；} .数学表 td {边框:1px 实心# 5fb962 文本对齐:向左！重要；填充:8px} .数学表 th {边框:1px 实心# 5fb962 填充:8px} .数学表 tr>th{背景色:# c6ebd9 垂直对齐:中间；} .数学表 tr:第 n 个子(奇数){背景色:# ffffff}

<figure class="table">

| 字段名 | 描述 |
| --- | --- |
| [布林栏位](https://www.geeksforgeeks.org/boolean-fields-in-serializers-django-rest-framework/#booleanfield) | 用于包装真值或假值的布尔字段。 |
| [零乌头田](https://www.geeksforgeeks.org/boolean-fields-in-serializers-django-rest-framework/#nullbooleanfield) | 接受真、假和空值的布尔字段。 |
| [夏菲尔德](https://www.geeksforgeeks.org/string-fields-in-serializers-django-rest-framework/#charfield) | CharField 用于存储文本表示。 |
| [EmailField](https://www.geeksforgeeks.org/string-fields-in-serializers-django-rest-framework/#emailfield) | EmailField 也是一种文本表示，它验证文本是有效的电子邮件地址。 |
| [regexffield](https://www.geeksforgeeks.org/string-fields-in-serializers-django-rest-framework/#regexfield) | 正如名称所定义的，RegexField 将字符串与特定的 regex 匹配，否则会引发错误。 |
| 尖叫场 | URLField 基本上是一个正则表达式字段，它根据 URL 匹配模式验证输入。 |
| [斯拉格菲尔德](https://www.geeksforgeeks.org/url-fields-in-serializers-django-rest-framework/#slugfield) | SlugField 是一个 RegexField，它根据模式[a-zA-Z0-9_-]+，验证输入。 |
| ipaddress field | IPAddressField 是确保输入是有效的 IPv4 或 IPv6 字符串的字段。 |
| [整数文件](https://www.geeksforgeeks.org/numeric-fields-in-serializers-django-rest-framework/#integerfield) | IntegerField 基本上是一个整数字段，它根据 Python 的 int 实例验证输入。 |
| [浮动字段](https://www.geeksforgeeks.org/numeric-fields-in-serializers-django-rest-framework/#floatfield) | FloatField 基本上是一个浮动字段，它根据 Python 的 float 实例验证输入。 |
| [十进制字段](https://www.geeksforgeeks.org/numeric-fields-in-serializers-django-rest-framework/#decimalfield) | 十进制字段基本上是一个十进制字段，它根据 Python 的十进制实例验证输入。 |
| [日期时间字段](https://www.geeksforgeeks.org/date-and-time-fields-in-serializers-django-rest-framework/#datetimefield) | DateTimeField 是用于日期和时间表示的序列化程序字段。 |
| 约会场 | 日期字段是用于日期表示的序列化程序字段。 |
| [时间域](https://www.geeksforgeeks.org/date-and-time-fields-in-serializers-django-rest-framework/#timefield) | Timefield 是用于时间表示的序列化程序字段。 |
| 耐久性场 | 持续时间字段是用于持续时间表示的序列化程序字段。 |
| [选择字段](https://www.geeksforgeeks.org/choice-selection-fields-in-serializers-django-rest-framework/#choicefield) | ChoiceField 基本上是一个字符域，它根据一组有限选项中的一个值来验证输入。 |
| [多选择字段](https://www.geeksforgeeks.org/choice-selection-fields-in-serializers-django-rest-framework/#multiplechoicefield) | MultipleChoiceField 基本上是一个字符域，它根据从一组有限的选项中选择的一组零个、一个或多个值来验证输入。 |
| [文件字段](https://www.geeksforgeeks.org/file-upload-fields-in-serializers-django-rest-framework/#filefield) | FileField 基本上是一种文件表示。它执行 Django 的标准文件字段验证。 |
| [图像场](https://www.geeksforgeeks.org/file-upload-fields-in-serializers-django-rest-framework/#imagefield) | ImageField 是一种图像表示。它验证上传的文件内容是否与已知的图像格式相匹配。 |
| 上市场 | 列表字段基本上是一个列表字段，它根据对象列表验证输入。 |
| [JSONField](https://www.geeksforgeeks.org/jsonfield-in-serializers-django-rest-framework/) | JSONField 基本上是一个字段类，用于验证传入的数据结构是否由有效的 JSON 原语组成。 |
| [隐藏字段](https://www.geeksforgeeks.org/hiddenfield-in-serializers-django-rest-framework/) | HiddenField 是一个字段类，它不根据用户输入取值，而是从默认值或可调用值中取值。 |
| 听写场 | DictField 基本上是一个字典字段，它根据对象字典验证输入。 |

</figure>

## 序列化程序字段中的核心参数

Django 中的序列化程序字段与 Django 表单字段和 Django 模型字段相同，因此需要某些参数来操作这些字段的行为。

。数学表{边框折叠:折叠；宽度:100%；} .数学表 td {边框:1px 实心# 5fb962 文本对齐:向左！重要；填充:8px} .数学表 th {边框:1px 实心# 5fb962 填充:8px} .数学表 tr>th{背景色:# c6ebd9 垂直对齐:中间；} .数学表 tr:第 n 个子(奇数){背景色:# ffffff}

<figure class="table">

| 争吵 | 描述 |
| --- | --- |
| [只读](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#read_only) | 将该值设置为 True 以确保在序列化表示时使用该字段，但在反序列化期间创建或更新实例时不使用该字段 |
| [只写 _ 条](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#write_only) | 将此设置为“真”，以确保该字段可以在更新或创建实例时使用，但在序列化表示时不包括在内。 |
| [必需](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#required) | 将此设置为 False 还允许在序列化实例时从输出中省略对象属性或字典键。 |
| [默认](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#default) | 如果设置，这将给出默认值，如果未提供输入值，该默认值将用于该字段。 |
| [允许 _ 空](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#allow_null) | 通常情况下，如果将“无”传递给序列化程序字段，将会引发错误。如果“无”应被视为有效值，则将此关键字参数设置为“真”。 |
| [来源](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#source) | 将用于填充字段的属性的名称。 |
| [验证器](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#validators) | 应该应用于输入字段输入的验证函数列表，这些函数要么引发验证错误，要么简单地返回。 |
| [错误信息](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#error_messages) | 错误信息的错误代码字典。 |
| 标签 | 一个短文本字符串，可用作 HTML 表单字段或其他描述性元素中的字段名称。 |
| [帮助 _ 文字](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#help_text) | 一个文本字符串，可用作 HTML 表单字段或其他描述性元素中字段的描述。 |
| [初始](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/#initial) | 应该用于预先填充 HTML 表单字段值的值。 |

</figure>