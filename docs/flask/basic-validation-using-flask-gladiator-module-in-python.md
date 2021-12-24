# 使用 Python 中的烧瓶-角斗士模块进行基本验证

> 原文:[https://www . geesforgeks . org/basic-验证-使用-烧瓶-角斗士-python 中的模块/](https://www.geeksforgeeks.org/basic-validation-using-flask-gladiator-module-in-python/)

考虑到所有进出系统的非结构化数据，现在各种验证都是必不可少的。除了客户端验证，服务器端验证在 web 开发中也同样重要。本文讨论了一种在各种框架(如 Flask 或 Django)中注入验证的方法。

Python 的**烧瓶-角斗士**是一个提供以下功能的模块:

*   允许任何形式的服务器端验证。
*   可以扩展到任何。py 框架。
*   允许检查范围、要求、类型等功能。

### 安装

这个模块没有内置 python，因此必须显式安装

> pip 安装烧瓶-角斗士

在本模块中，validate()函数用于完成工作。

> **语法:**
> 
> 验证(数据、验证器)

**参数:**

*   ***数据:**考虑中的数据*
*   **验证器:**告知必须在什么基础上进行验证
    *   **必需:**总是需要验证器来检查字段的存在。
    *   **format_email :** 检查邮件的验证器。
    *   **长度 _ 最大值**:检查文本的最大长度。
    *   **长度 _ 分钟**:检查最小文本长度。
    *   **长度:**检查特定长度。
    *   **类型 _** :检查特定类型。
    *   **正则表达式 _ :** 检查正则表达式。
    *   **_ 值**:检查特定值。
    *   _ 中的**:特定列表中的检查。**
    *   **lt** :检查小于整数值。
    *   **gt** :检查是否大于整数值。
    *   **等式**:检查相等的整数值。
    *   **ne** :检查不相等的整数值。
    *   **gte** :检查大于等于的整数值。
    *   **lte** :检查小于等于整数值。
    *   **true_if_empty** :如果为空，则该验证器返回 true。
    *   **skip_on_fail** :如果验证失败，可以用这个跳过测试进行验证。

**进场:**

*   在初始步骤中，输入数据以字典格式表示。
*   验证被初始化为元组的元组，其中元组的第一个元素是要检查的键，接下来的值是应该应用于相应键的验证。
*   validate()函数接受验证和输入字典，如果所有验证都为真，则返回 True，否则返回 False。

下面给出了基于不同验证器执行验证的各种实现。

**例 1 :**

## 蟒蛇 3

```
import gladiator as gl

# input test data
valid_data = {
    'email': 'manjeet@gfg.com',
    'password': '123456',
    'name': 'Manjeet',
    'age': 24,
    'access': "User"
}

# assigning validations
field_validations = (
    ('email', gl.required, gl.format_email),
    ('password', gl.required, gl.length_min(5)),
    ('name', gl.required, gl.type_(str)),
    ('age', gl.required, gl.type_(int), gl.eq(24)),
    ('access', gl.required, gl.in_(['User', 'Admin']))
)

# checking data using validate()
print("Validating data : ")
result = gl.validate(field_validations, valid_data)
print("Is data valid ? : " + str(bool(result)))
```

**输出:**

> 验证数据:
> 
> 数据有效吗？:真

**例 2 :**

## 蟒蛇 3

```
# Using regex, gt and length validators
import gladiator as gl

# input test data
valid_data = {
    'email': 'manjeet@gfg.com',
    'password': '123456',
    'name': 'Manjeet',
    'Gender': 'M',
    'age': 24,

}

# assigning validations
# checks name by regex, gender using length range, age greater than 18.
field_validations = (
    ('email', gl.required, gl.format_email),
    ('password', gl.required, gl.length_min(5)),
    ('name', gl.required, gl.type_(str), gl.regex_('[a-zA-Z][a-zA-Z ]+')),
    ('age', gl.required, gl.type_(int), gl.gt(18)),
    ('Gender', gl.length(1, 4)),
)

# checking data using validate()
print("Validating data : ")
result = gl.validate(field_validations, valid_data)
print("Is data valid ? : " + str(bool(result)))
```

**输出:**

> 验证数据:
> 
> 数据有效吗？:真