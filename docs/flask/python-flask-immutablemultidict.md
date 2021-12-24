# python flask–不变多维

> 原文:[https://www . geeksforgeeks . org/python-flask-immigrate multiticict/](https://www.geeksforgeeks.org/python-flask-immutablemultidict/)

与普通字典不同，多字典是字典的一个子类，可以包含同一个键的多个值。之所以使用它，是因为一些表单元素对同一个键有多个值，并且它以列表的形式保存一个键的多个值。

**例:**

## 蟒 3

```py
from werkzeug.datastructures import MultiDict

orders = MultiDict([(1, 'GFG'), (1, 'Geeks')])
print(orders[1])

print(orders.getlist(1))
```