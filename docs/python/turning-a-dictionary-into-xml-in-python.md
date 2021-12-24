# 用 Python 把字典变成 XML

> 原文:[https://www . geesforgeks . org/turing-a-dictionary-in-XML-python/](https://www.geeksforgeeks.org/turning-a-dictionary-into-xml-in-python/)

**XML** 代表**可扩展标记语言**。XML 被设计成自我描述的，用于存储和传输数据。XML 标签用于识别、存储和组织数据。XML 文档的基本构造块是由标签定义的。一个元素有一个开始标记和一个结束标记。XML 中的所有元素都包含在称为根元素的最外层元素中。

**示例:**

```py
<geeksforgeeks>
<course>DSA</course>
<price>2499/-</price>
</geeksforgeeks>
```

在上例中，geeksforgeeks 是根元素，<course>、<price>、<price>是元素。</price></price></course>

**现在，让我们来看看如何将字典转换为 XML:**
要在 Python 中将字典转换为 XML，我们将使用 **xml.etree.ElementTree** 库。xml.etree.ElementTree 库通常用于解析，也用于创建 xml 文档。使用**元素树**类包装一个组件结构，并将其从和转换为 XML。这种转换的结果是一个**元素**。对于输入/输出，使用 xml.etree.ElementTree 中的 **tostring()** 函数可以很容易地将其转换为字节字符串。

### **XML . etree . element tree . element()****Class:**

这个元素类定义了元素接口，并提供了这个接口的引用实现。

> **语法:**元素(标记，attrib = {}，* *额外)
> 
> **参数:**
> 
> *   **标签:**这是一个字符串，标识这个元素代表什么样的数据。
> *   **attrib:** 这是一个可选字典，包含元素属性。
> *   *** *额外:**这包含附加属性，作为关键字参数给出。
> 
> **返回:**元素对象

### **XML . etree . element tree . tostring()****功能:**

该函数生成一个 XML 元素的字符串表示形式。

> **语法:** tostring(元素)
> 
> **参数:** XML 元素
> 
> **返回:**XML 元素的字符串表示形式

### **ElementObject.set()** **方法:**

此方法将元素的属性键设置为值。

> **语法:**设置(键，值)
> 
> **参数:**
> 
> *   **键:**代表属性。
> *   **值:**代表属性的值。
> 
> **返回:**无

现在，让我们看看将字典转换为 XML 的 python 程序:

## 蟒蛇 3

```py
# import Element class, tostring function
# from xml.etree.ElementTree library
from xml.etree.ElementTree import Element,tostring

# define a function to
# convert a simple dictionary
# of key/value pairs into XML
def dict_to_xml(tag, d):

    elem = Element(tag)
    for key, val in d.items():
        # create an Element
        # class object
        child = Element(key)
        child.text = str(val)
        elem.append(child)

    return elem

# Driver Program
s = { 'name': 'geeksforgeeks',
     'city': 'noida', 'stock': 920 }

# e stores the element instance
e = dict_to_xml('company', s)

# Element instance is different
# every time you run the code
print(e)

# converting into a byte string
print(tostring(e))

# We can attach attributes
# to an element using
# set() method
e.set('_id','1000')

print(tostring(e))
```

**输出:**

> <element at="">b' <公司> <名称>geeksforgeeks</名称> <城市>诺伊达</城市> <股票>920</股票></公司> '
> b' <公司 _ id = " 1000 "><名称>geekforges<</element>