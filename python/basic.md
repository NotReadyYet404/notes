## 字符串
- 将列表内容拼接成字符串
```python
great_list = [......]
string = "".join(great_list)

```
- 删除字符串中的某些位置的字符
```python
# 以删除前四个字符为例
string = "........"
str_list = list(string)
del str_list[0:4]
string = str(str_list)

```

## 字典
- 判断字典中是否有某个键：
```python
dic = {......}
great = somevalue
if great in dic.keys():
	print('in')
else:
	print('not in')

```

## JSON
- 将符合json格式的字符串转换成json对象
```python
import json


string = '{.......}'
json_obj = json.loads(string)

```

## 网络
### 使用urllib.request下载文件

```python
ulrllib.request.urlretrieve(url, filename=filename)
```

## 系统(OS)

### 判断系统中是否存在某个文件
```python
import os

filepath = '/.../.../filename'
if os.path.exists(filepath):
	print('EXISTS')
else:
	print('NOT FOUND')
```

### 执行系统命令
```python
import os

command = '......'
os.system(command)

```

