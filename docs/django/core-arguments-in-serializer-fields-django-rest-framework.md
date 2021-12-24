# 序列化程序字段中的核心参数–姜戈 REST 框架

> 原文:[https://www . geesforgeks . org/core-arguments-in-serializer-fields-django-rest-framework/](https://www.geeksforgeeks.org/core-arguments-in-serializer-fields-django-rest-framework/)

Django 中的序列化程序字段与 Django 表单字段和 Django 模型字段相同，因此需要某些参数来操作这些字段的行为。在 Django REST 框架中，序列化的概念就是将数据库数据转换成 javascript 可以使用的数据类型。本文围绕序列化程序字段可以用来高效地操纵序列化程序内外的数据的各种参数展开。

## 序列化程序字段中的核心参数

。数学表{边框折叠:折叠；宽度:100%；} .数学表 td {边框:1px 实心# 5fb962 文本对齐:向左！重要；填充:8px} .数学表 th {边框:1px 实心# 5fb962 填充:8px} .数学表 tr>th{背景色:# c6ebd9 垂直对齐:中间；} .数学表 tr:第 n 个子(奇数){背景色:# ffffff}

<figure class="table">

| 争吵 | 描述 |
| --- | --- |
| [只读](#read_only) | 将该值设置为 True 以确保在序列化表示时使用该字段，但在反序列化期间创建或更新实例时不使用该字段 |
| [只写 _ 条](#write_only) | 将此设置为“真”，以确保该字段可以在更新或创建实例时使用，但在序列化表示时不包括在内。 |
| [必需](#required) | 将此设置为 False 还允许在序列化实例时从输出中省略对象属性或字典键。 |
| [默认](#default) | 如果设置，这将给出默认值，如果未提供输入值，该默认值将用于该字段。 |
| [允许 _ 空](#allow_null) | 通常情况下，如果将“无”传递给序列化程序字段，将会引发错误。如果“无”应被视为有效值，则将此关键字参数设置为“真”。 |
| [来源](#source) | 将用于填充字段的属性的名称。 |
| [验证器](#validators) | 应该应用于输入字段输入的验证函数列表，这些函数要么引发验证错误，要么简单地返回。 |
| [错误信息](#error_messages) | 错误信息的错误代码字典。 |
| 标签 | 一个短文本字符串，可用作 HTML 表单字段或其他描述性元素中的字段名称。 |
| [帮助 _ 文字](#help_text) | 一个文本字符串，可用作 HTML 表单字段或其他描述性元素中字段的描述。 |
| [初始](#initial) | 应该用于预先填充 HTML 表单字段值的值。 |

</figure>

#### 只读

只读字段包含在应用编程接口输出中，但不应包含在创建或更新操作的输入中。序列化程序输入中错误包含的任何“只读”字段都将被忽略。

将该值设置为 True 以确保在序列化表示时使用该字段，但在反序列化期间创建或更新实例时不使用该字段。

默认为假
**语法–**

```
read_only = True/False
```

**示例–**

```
field_name = serializers.CharField(read_only = True) 
```

#### 只写

将此设置为“真”，以确保该字段可以在更新或创建实例时使用，但在序列化表示时不包括在内。

默认为假
**语法–**

```
write_only = True/False
```

**示例–**

```
field_name = serializers.CharField(write_only = True) 
```

#### 需要

通常，如果在反序列化过程中没有提供字段，将会引发错误。如果反序列化期间不要求该字段存在，则设置为 false。

将此设置为 False 还允许在序列化实例时从输出中省略对象属性或字典键。如果键不存在，它将不会包含在输出表示中。

默认为真。

**语法–**

```
write_only = True/False
```

**示例–**

```
field_name = serializers.CharField(write_only = True) 
```

#### 系统默认值

如果设置，这将给出默认值，如果未提供输入值，该默认值将用于该字段。如果没有设置，默认行为是根本不填充属性。

部分更新操作期间不应用默认值。在部分更新的情况下，只有在传入数据中提供的字段才会返回经过验证的值。

可以设置为函数或其他可调用的，在这种情况下，每次使用该值时都会对其进行计算。当被调用时，它将不会接收任何参数。如果可调用具有 requires_context = True 属性，则序列化程序字段将作为参数传递。

例如:

```
class CurrentUserDefault:
    """
    May be applied as a `default=...` value on a serializer field.
    Returns the current user.
    """
    requires_context = True

    def __call__(self, serializer_field):
        return serializer_field.context['request'].user
When serializing the instance, default will be used if the o
```

实例中不存在对象属性或字典键。

请注意，设置默认值意味着该字段不是必需的。同时包含默认和必需的关键字参数是无效的，并且会引发错误。

**语法–**

```
default = value
```

**示例–**

```
field_name = serializers.CharField(default = "Naveen") 
```

#### 允许 _null

通常情况下，如果将“无”传递给序列化程序字段，将会引发错误。如果“无”应被视为有效值，则将此关键字参数设置为“真”。

请注意，如果没有明确的默认值，将此参数设置为 True 将意味着序列化输出的默认值为 null，但并不意味着输入反序列化的默认值。

默认为假

**语法–**

```
allow_null = True/False
```

**示例–**

```
field_name = serializers.CharField(allow_null = True) 
```

#### 来源

将用于填充字段的属性的名称。可能是一种只接受自身参数的方法，如 URL field(source = ' get _ absolute _ URL ')，也可能使用虚线表示法来遍历属性，如 EmailField(source='user.email ')。当用点符号序列化字段时，如果在属性遍历期间没有任何对象或者对象为空，则可能需要提供默认值。

值 source='* '有特殊的含义，用于指示整个对象应该传递到字段。这对于创建嵌套表示很有用，或者对于需要访问完整对象以确定输出表示的字段很有用。

默认为字段名称。

**语法–**

```
source = value
```

**示例–**

```
field_name = serializers.CharField(source = "user.name") 
```

#### 验证器

应该应用于输入字段输入的验证函数列表，这些函数要么引发验证错误，要么简单地返回。验证器函数通常应该引发序列化程序。ValidationError，但也支持 Django 的内置 ValidationError，以便与 Django 代码库中或第三方 Django 包中定义的验证器兼容。

**语法–**

```
validators = [function_1, function_2]
```

**示例–**

```
field_name = serializers.CharField(validations = [validate_name, validate_username]) 
```

#### 错误消息

错误信息的错误代码字典。它的工作方式与[错误消息相同–姜戈内置字段验证](https://www.geeksforgeeks.org/error_messages-django-built-in-field-validation/)
**语法–**

```
error_messages = {'argument':'message'}
```

**示例–**

```
field_name = serializers.CharField(error_messages = {"unique":"Data should be unique"}) 
```

#### 标签

一个短文本字符串，可用作 HTML 表单字段或其他描述性元素中的字段名称。与[标签相同-姜戈表单域验证](https://www.geeksforgeeks.org/label-django-form-field-validation/)

**语法–**

```
label = value
```

**示例–**

```
field_name = serializers.CharField(label = "Name") 
```

#### 帮助 _ 文本

一个文本字符串，可用作 HTML 表单字段或其他描述性元素中字段的描述。与[help _ text-Django 内置字段验证](https://www.geeksforgeeks.org/help_text-django-built-in-field-validation/)相同。
**语法–**

```
help_text = value
```

**示例–**

```
field_name = serializers.CharField(help_text = "Enter only 10 characters") 
```

#### 最初的

应该用于预先填充 HTML 表单字段值的值。与[初始-姜戈表单域验证](https://www.geeksforgeeks.org/initial-django-form-field-validation/)相同。您可以向它传递一个可调用的，就像您可以对任何常规的姜戈字段做的那样:
**语法–**

```
initial = value
```

**示例–**

```
import datetime
from rest_framework import serializers
class ExampleSerializer(serializers.Serializer):
    day = serializers.DateField(initial=datetime.date.today)
```