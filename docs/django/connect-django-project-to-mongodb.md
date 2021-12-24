# 将 Django 项目连接到 MongoDB

> 原文:[https://www . geesforgeks . org/connect-django-project-to-MongoDB/](https://www.geeksforgeeks.org/connect-django-project-to-mongodb/)

Djongo 是一个 SQL 到 mongodb 的查询传输器。使用 djongo，我们可以使用 MongoDB 作为我们的 Django 项目的后端数据库。我们甚至不需要改变 Django ORM。最棒的是，我们只需添加一行代码就可以用 MongoDB 设置 Django。不需要更改序列化程序、视图或任何其他模块。

**正式文件–**[https://pypi.org/project/djongo/](https://pypi.org/project/djongo/)

**Working–**
Djongo 将一个 SQL 查询字符串翻译成 MongoDB 查询文档。因此，不需要更改模型、序列化程序、视图或任何 Django 特性。Djongo 支持所有 django contrib 库，这使得它成为一个易于使用的连接器。

![](img/686752e8ab0c4740dfe495ace313bbc3.png)

**要求–**

1.Python 3.6 或更高版本。

2.MongoDB 3.4 或更高版本。(如果使用嵌套查询，则需要 MongoDB 3.6 或更高版本。)

**特征:**

*   **重用 Django 模型/ORM–**
    由于 Django 模型与 Djongo 兼容，我们可以使用重用它们。
*   **完整性检查**
    Djongo 允许在保存到数据库之前进行完整性检查，如缺失值。
    对于 eg-如果我们在 EmbeddedField 中设置 null=False，blank=False，则不会存储缺失值

![](img/3d0792135b64841aca684350adce8af5.png)

*   **验证器**
    我们可以应用像 URLValidator、EmailValidator、RegexValidator 等验证检查。在每个字段保存到数据库之前。

![](img/08e5a9d1ce3f507566aeff7f09f58d0b.png)

用法:

**第一步:设置虚拟环境**

```
virtualenv myenv
myenv\Scripts\activate
```

![](img/5b348b1eb5825fc5187440c9ff0b1218.png) ![](img/e5b88225cad0914b7147839d22fc0a52.png)

**第二步:安装 Django**

```
pip install django
```

![](img/fd92e4f37fcf024f908c54ba6b20dd3a.png)

**第三步:安装 Djongo**

```
pip install djongo
```

![](img/c0498d8e6b86aa3b6aa3198f4ac76ed9.png)

**第四步:启动姜戈项目**

```
django-admin startproject geeks_project
```

![](img/3f955dcc82b55508dbcfc0e3451ac6d5.png)

您的项目结构如下所示:

![](img/1cba77d79c369d5febc691ee5c4a2bde.png)

**第五步:更改设置. py 文件**

现在，打开**设置. py** 文件。注释掉或删除以前的 SQL 数据库配置，并在**设置中添加以下代码**

```
   DATABASES = {
      'default': {
          'ENGINE': 'djongo',
          'NAME': 'your-database-name',
      }
  }
```

![](img/4c95d8b9396b7a6392d6331b456fe1a2.png)

就这样。现在，您可以使用 Mongodb 作为 django 项目的后端数据库，而无需更改单个 django 模型！