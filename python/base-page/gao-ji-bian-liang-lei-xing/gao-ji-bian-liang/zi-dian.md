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

## 字典内置函数 & 方法

Python字典包含了以下内置函数：

<table><thead><tr><th width="184">序号</th><th>函数及描述</th></tr></thead><tbody><tr><td>1</td><td><a href="https://www.runoob.com/python/att-dictionary-cmp.html">cmp(dict1, dict2)</a><br>比较两个字典元素。</td></tr><tr><td>2</td><td><a href="https://www.runoob.com/python/att-dictionary-len.html">len(dict)</a><br>计算字典元素个数，即键的总数。</td></tr><tr><td>3</td><td><a href="https://www.runoob.com/python/att-dictionary-str.html">str(dict)</a><br>输出字典可打印的字符串表示。</td></tr><tr><td>4</td><td><a href="https://www.runoob.com/python/att-dictionary-type.html">type(variable)</a><br>返回输入的变量类型，如果变量是字典就返回字典类型。</td></tr></tbody></table>

Python字典包含了以下内置方法：

<table><thead><tr><th width="178">序号</th><th>函数及描述</th></tr></thead><tbody><tr><td>1</td><td><a href="https://www.runoob.com/python/att-dictionary-clear.html">dict.clear()</a><br>删除字典内所有元素</td></tr><tr><td>2</td><td><a href="https://www.runoob.com/python/att-dictionary-copy.html">dict.copy()</a><br>返回一个字典的浅复制</td></tr><tr><td>3</td><td><a href="https://www.runoob.com/python/att-dictionary-fromkeys.html">dict.fromkeys(seq[, val])</a><br>创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值</td></tr><tr><td>4</td><td><a href="https://www.runoob.com/python/att-dictionary-get.html">dict.get(key, default=None)</a><br>返回指定键的值，如果值不在字典中返回default值</td></tr><tr><td>5</td><td><a href="https://www.runoob.com/python/att-dictionary-has_key.html">dict.has_key(key)</a><br>如果键在字典dict里返回true，否则返回false。Python3 不支持。</td></tr><tr><td>6</td><td><a href="https://www.runoob.com/python/att-dictionary-items.html">dict.items()</a><br>以列表返回可遍历的(键, 值) 元组数组</td></tr><tr><td>7</td><td><a href="https://www.runoob.com/python/att-dictionary-keys.html">dict.keys()</a><br>以列表返回一个字典所有的键</td></tr><tr><td>8</td><td><a href="https://www.runoob.com/python/att-dictionary-setdefault.html">dict.setdefault(key, default=None)</a><br>和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default</td></tr><tr><td>9</td><td><a href="https://www.runoob.com/python/att-dictionary-update.html">dict.update(dict2)</a><br>把字典dict2的键/值对更新到dict里</td></tr><tr><td>10</td><td><a href="https://www.runoob.com/python/att-dictionary-values.html">dict.values()</a><br>以列表返回字典中的所有值</td></tr><tr><td>11</td><td><a href="https://www.runoob.com/python/python-att-dictionary-pop.html">pop(key[,default])</a><br>删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。</td></tr><tr><td>12</td><td><a href="https://www.runoob.com/python/python-att-dictionary-popitem.html">popitem()</a><br>返回并删除字典中的最后一对键和值。</td></tr></tbody></table>

