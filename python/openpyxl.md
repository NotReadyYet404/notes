## openpyxl
是一个专门操纵Excel文件内容的第三方库


### 创建Excel文件
openpyxl一切的起点是Workbook，所以先创建Workbook实例然后再保存，就完成了创建Excel文件
```python
from openpyxl import Workbook

wb = Workbook()
wb.save('file_path')
```


### 读取Excel文件
```python
from openpyxl import load_workbook

wb = load_workbook('file_path')
```

### 获取sheet名称列表
```python
from openpyxl import load_workbook

wb = load_workbook('file_path')

sheetnames_list = wb.sheetnames
```

### 创建/获取sheet
```python
from openpyxl import load_workbook

wb = load_workbook('file_path')
# 根据sheet名获取sheet实例
ws = wb['sheetname']
# 根据sheet名创建sheet实例
ws = wb.create_sheet('sheet_name')

# ! 一定不要忘记将实例保存到文件
wb.save('file_path')
```

### 读/写单元格
```python
from openpyxl import load_workbook

ws = load_workbook('file_path')['sheet_name']
# 根据行号获取整行，结果为单元格列表
row = ws['2']
# 根据列号获取整列，结果为单元格列表
column = ws['A']
# 获取单元格
cell = ws['A3']

# 获取单元格数据
cell.value

# 向单元格写入数据
## method 1
cell.value = 数据
## method 2
ws.cell(row=row_num, column=column_num, value=数据)

# 如果写入数据了一定不要忘记保存！
wb.save('file_path')
```


### 行列操作
#### 添加/删除行
```python
from openpyxl import Workbook
wb = Workbook()  # 默认生成一个名为Sheet的sheet
 
# 创建sheet
for name in ['a','b']:
    ws = wb.create_sheet(name)
 
# 追加行
for sheet in wb:
    for i in range(1,5):
        sheet.append(['a'+str(i),'b'+str(i)])
 
# 删除第一行
for sheet in wb:
    sheet.delete_rows(1)
 
# 删除从1到3行
for sheet in wb:
    sheet.delete_rows(1,3)
 
wb.save('test.xlsx')
```


### 样式
#### 设置单元格背景颜色
以设置十六进制1874CD颜色值为例
```python
fill = openpyxl.styles.PatternFill("solid", fgColor="1874CD")
ws.cell(row=row_num, column=column_num).fill = fill
```
#### 设置单行和一列的长宽
```python
from openpyxl import load_workbook
 
wb = load_workbook('test.xlsx')
print(wb.sheetnames)
ws = wb[wb.sheetnames[0]]
 
# 调整列宽
ws.column_dimensions['A'].width = 20.0
 
# 调整行高
ws.row_dimensions[1].height = 40
 
wb.save('test.xlsx')
```


#### 设置单元格字体颜色
```python
from openpyxl.styles import Font

# 字体格式，颜色和大小
font_pass = Font(size=16, bold=True, color="00FF00")
font_false = Font(size=16, bold=True, color="FF0000")

# 新建工作簿
data = openpyxl.Workbook() 
# 添加页,设置第一个工作页
data.create_sheet('Report',0)  
# 获得当前活跃的工作页，默认为第一个工作页
table = data.active 

# 设置字体大小和颜色
table.cell(row=nrows + 1, column=col).font = font_false
```


#### 设置sheet的缩放比例
```python
from openpyxl import load_workbook

excel = load_workbook("../demo.xlsx", data_only=False)

ws = excel.active
ws.views.sheetView[0].zoomScale = 50

excel.save("./test.xlsx")
```

