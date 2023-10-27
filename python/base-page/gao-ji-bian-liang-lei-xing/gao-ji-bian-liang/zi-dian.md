# 字典

字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值 key:value 对用冒号 : 分割，每个键值对之间用逗号 , 分割，整个字典包括在花括号 {} 中

```python
d = {key1 : value1, key2 : value2 }
```

**注意：**dict 作为 Python 的关键字和内置函数，变量名不建议命名为 **dict**。

键一般是唯一的，如果重复最后的一个键值对会替换前面的，值不需要唯一

## 访问字典里的值

```python
tinydict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
 
print "tinydict['Name']: ", tinydict['Name']
print "tinydict['Age']: ", tinydict['Age']

>>> tinydict['Name']:  Zara
>>> tinydict['Age']:  7
```

## 修改字典

想字典添加新内容的方法是增加新的键/值对。

```python
tinydict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
 
tinydict['Age'] = 8 # 更新
tinydict['School'] = "RUNOOB" # 添加
 
 
print "tinydict['Age']: ", tinydict['Age']
print "tinydict['School']: ", tinydict['School']

>>> tinydict['Age']:  8
>>> tinydict['School']:  RUNOOB

```

## 删除字典元素

用del命令删除

```python
tinydict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
 
del tinydict['Name']  # 删除键是'Name'的条目
tinydict.clear()      # 清空字典所有条目
del tinydict          # 删除字典
```

## 字典键的特性

1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住

2）键必须不可变，所以可以用数字，字符串或元组充当，所以用列表就不行
