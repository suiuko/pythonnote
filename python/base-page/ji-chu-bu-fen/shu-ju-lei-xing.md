# 数据类型

* Numbers（数字）
* String（字符串）
* List（列表）
* Tuple（元组）
* Dictionary（字典）

## &#x20;1. 字符串

```python
s = "nihao"
```

python的字串列表有2种取值顺序:

* 从左到右索引默认0开始的，最大范围是字符串长度少1
* 从右到左索引默认-1开始的，最大范围是字符串开头

<figure><img src="https://www.runoob.com/wp-content/uploads/2013/11/python-string-slice.png" alt=""><figcaption></figcaption></figure>

实现从字符串中截取一段子字符串的话，可以使用\[头下标:尾下标] 来截取相应的字符串，下标从 0 开始。

<figure><img src="https://www.runoob.com/wp-content/uploads/2013/11/o99aU.png" alt=""><figcaption></figcaption></figure>

加号（+）是字符串连接运算符，星号（\*）是重复操作。

### 截取可以接受三个参数

\[头下标：尾下标：步长]

<figure><img src="https://www.runoob.com/wp-content/uploads/2013/11/python_list_slice_2.png" alt=""><figcaption></figcaption></figure>

## 2. 列表 list

```python
list = ['nihao', 786, 2]
```

列表用 \[ ] 标识，列表中值的切割也可以用到变量 \[头下标:尾下标] ，就可以截取相应的列表，从左到右索引默认 0 开始，从右到左索引默认 -1 开始，下标可以为空表示取到头或尾。

> 注意是左闭右开！

<figure><img src="https://www.runoob.com/wp-content/uploads/2014/08/list_slicing1_new1.png" alt=""><figcaption></figcaption></figure>

## 3. 元组 tuple

元组用 () 标识。内部元素用逗号隔开。但是元组不能二次赋值，相当于只读列表

```python
tuple = ('nihao',7864,70.2)
```

## 4. 字典

字典(dictionary)是除列表以外python之中最灵活的内置数据结构类型。列表是有序的对象集合，字典是无序的对象集合。

两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。

字典用"{ }"标识。字典由索引(key)和它对应的值value组成。

```python
dict = {}
dict['one'] = "this is one"

tinydict = {'name':'nihao','code':123,'dept':'sales'}
print tinydict             # 输出完整的字典
print tinydict.keys()      # 输出所有键
print tinydict.values()    # 输出所有值
```

## python 数据类型转换

<table><thead><tr><th width="223.5">函数</th><th>描述</th></tr></thead><tbody><tr><td><a href="https://www.runoob.com/python/python-func-int.html">int(x [,base])</a></td><td>将x转换为一个整数</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-long.html">long(x [,base] )</a></td><td>将x转换为一个长整数</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-float.html">float(x)</a></td><td>将x转换到一个浮点数</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-complex.html">complex(real [,imag])</a></td><td>创建一个复数</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-str.html">str(x)</a></td><td>将对象 x 转换为字符串</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-repr.html">repr(x)</a></td><td>将对象 x 转换为表达式字符串</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-eval.html">eval(str)</a></td><td>用来计算在字符串中的有效Python表达式,并返回一个对象</td></tr><tr><td><a href="https://www.runoob.com/python/att-tuple-tuple.html">tuple(s)</a></td><td>将序列 s 转换为一个元组</td></tr><tr><td><a href="https://www.runoob.com/python/att-list-list.html">list(s)</a></td><td>将序列 s 转换为一个列表</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-set.html">set(s)</a></td><td>转换为可变集合</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-dict.html">dict(d)</a></td><td>创建一个字典。d 必须是一个序列 (key,value)元组。</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-frozenset.html">frozenset(s)</a></td><td>转换为不可变集合</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-chr.html">chr(x)</a></td><td>将一个整数转换为一个字符</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-unichr.html">unichr(x)</a></td><td>将一个整数转换为Unicode字符</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-ord.html">ord(x)</a></td><td>将一个字符转换为它的整数值</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-hex.html">hex(x)</a></td><td>将一个整数转换为一个十六进制字符串</td></tr><tr><td><a href="https://www.runoob.com/python/python-func-oct.html">oct(x)</a></td><td>将一个整数转换为一个八进制字符串</td></tr></tbody></table>
