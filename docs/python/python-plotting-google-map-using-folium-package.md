# Python |使用树叶包绘制谷歌地图

> 原文:[https://www . geesforgeks . org/python-绘图-谷歌-地图-使用-树叶-包/](https://www.geeksforgeeks.org/python-plotting-google-map-using-folium-package/)

[**leaf**](http://folium.readthedocs.io/en/latest/)是建立在 Python 生态系统的数据角力优势和 leaf . js(JavaScript)库的映射优势之上的。简单地说，在 Python 中操作您的数据，然后通过 leaf 在传单地图上可视化它。leaf 使得在交互式 leaf 地图上可视化用 Python 处理的数据变得很容易。这个库有许多来自 OpenStreetMap、Mapbox 等的内置波形图。
命令安装叶模块:

```
pip install folium
```

**代码#1 :** 创建基础地图。

## 蟒蛇 3

```
# import folium package
import folium

# Map method of folium return Map object

# Here we pass coordinates of Gfg
# and starting Zoom level = 12
my_map1 = folium.Map(location = [28.5011226, 77.4099794],
                                        zoom_start = 12 )

# save method of Map object will create a map
my_map1.save(" my_map1.html " )
```