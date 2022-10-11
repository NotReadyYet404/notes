## tabulate
Descrption: 格式化打印各种样式的表格
基本用法：
```python
>> from tabulate import tabulate

>> table=[["Sun",696000,1989100000], ["Earth",6371,5973.6],["Moon",1737,73.5], ["Mars",3390,641.85] ]
>>> print(tabulate(table, headers=["Planet","R (km)", "mass (x 10^29 kg)"]))
Planet      R (km)    mass (x 10^29 kg)
--------  --------  -------------------
Sun         696000           1.9891e+09
Earth         6371        5973.6
Moon          1737          73.5
Mars          3390         641.85
```
基本参数俩：第一个表格主体，传入一个二维列表作为参数；第二个是表格头，一个一维列表作为参数。

第三个参数：tablefmt='格式名'，用于指定格式化的格式，详细要去python-tabulate的GitHub仓库看了，我最喜欢的pipe，因为符合Markdown
表格格式，方便我时候整合到Markdown中，下面是pipe的一个样例：
```python
>>> print(tabulate(table, headers, tablefmt="pipe"))
| item   |   qty |
| name   |       |
|:-------|------:|
| eggs   |   451 |
| more   |    42 |
| spam   |       |
```
