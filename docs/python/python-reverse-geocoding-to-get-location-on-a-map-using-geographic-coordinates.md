# Python |反向地理编码使用地理坐标在地图上获取位置

> 原文:[https://www . geesforgeks . org/python-反向地理编码-使用地理坐标在地图上获取位置/](https://www.geeksforgeeks.org/python-reverse-geocoding-to-get-location-on-a-map-using-geographic-coordinates/)

反向地理编码是从给定的一对地理坐标(纬度和经度)中查找地点或位置地址的过程。
**所需模块:**

```py
reverse_geocoder: A Python library for offline reverse geocoding.
pprint: A module which helps to "pretty-print" any arbitrary python data structure.
```

**安装:**
使用 **pip** 可以轻松安装模块。

```py
pip install reverse_geocoder
pip install pprint
```

**例:**

```py
Input : (36.778259, -119.417931)
Output : 
Loading formatted geocoded file...
[{'admin1': 'California',
  'admin2': 'Fresno County',
  'cc': 'US',
  'lat': '36.72384',
  'lon': '-119.45818',
  'name': 'Minkler'}]
Input : (28.644800, 77.216721)
Output : 
Loading formatted geocoded file...
[{'admin1': 'NCT',
  'admin2': 'New Delhi',
  'cc': 'IN',
  'lat': '28.63576',
  'lon': '77.22445',
  'name': 'New Delhi'}]
```

下面是实现:

## 蟒蛇 3

```py
# Python3 program for reverse geocoding.

# importing necessary libraries
import reverse_geocoder as rg
import pprint

def reverseGeocode(coordinates):
    result = rg.search(coordinates)

    # result is a list containing ordered dictionary.
    pprint.pprint(result)

# Driver function
if __name__=="__main__":

    # Coordinates tuple.Can contain more than one pair.
    coordinates =(28.613939, 77.209023)

    reverseGeocode(coordinates)
```

**输出:**

```py
Loading formatted geocoded file...
[{'admin1': 'NCT',
  'admin2': 'New Delhi',
  'cc': 'IN',
  'lat': '28.63576',
  'lon': '77.22445',
  'name': 'New Delhi'}]
```

**参考文献:**

[https://www.latlong.net/](https://www.latlong.net/)