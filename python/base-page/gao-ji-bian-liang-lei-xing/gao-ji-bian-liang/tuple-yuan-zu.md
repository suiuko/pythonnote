# tuple 元组

元组中只包含一个元素时，需要在元素后面添加逗号

元组与字符串类似，下标索引从0开始，可以进行截取，组合等。

## 2.1 元组的定义

`tuple` （元组） 与 列表类似，不同之处在于 元组的 元素不能修改

元素的索引从`0` 开始，元组用 `()` 来定义

元组表示多个元素组成的序列

## 2.2 元组常用操作

```python
# 创建元组
info_tuple = ("zhangsan",18,1.75)

# 1. 取值和取索引
print(info_tuple[0])
print(info_tuple.index("zhangsan")) # 已经知道数据的内容，需要知道索引

# 2. 统计计数
print(info_tuple.count("zhangsan"))

# 统计元组中包含元素的个数
print(len(info_tuple))
```

## 2.2.1 修改元组

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合。

```python
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')

tup3 = tup1 + tup2
print tup3
>>> (12, 34.56, 'abc', 'xyz')
```

## 2.3 循环遍历

取值 就是从 元组 中获取存储在指定位置的数据

遍历 就是 从头到尾 依次 从 元组 中获取数据

```python
# for 循环内部使用的变量 in 元组
for item in info:
    循环内部针对元组元素进行操作
    print(item)
```

`for` 循环遍历所有非数字型类型的变量： 列表、元组、字典、字符串

## 2.3.1 访问元组

元组可以使用下标索引来访问元组中的值。

```python
tup1 = ('physics', 'chemistry', 1997, 2000)
print "tup1[0]: ", tup1[0]
```

## 2.4 应用场景

函数的 参数 和返回值，一个函数可以接受任意多个参数，或者 一次返回多个数据

格式字符串，格式化字符串后面的`()` 本质上就是一个元组

让列表不可以被修改，保证数据安全

```python
info_tuple = ("小明",18,1.75)

# 格式化字符串后面的 （） 本质上就是元组
print("%s 年龄是 %d 身高是 %.2f" % info_tuple)
```

#### 元组和列表之前的转换

使用 `list` 函数可以把元组转换成列表

```python
list(元组)
```

使用`tuple` 函数可以把列表转换成元组

```python
tuple(列表)
```

## 2.5 元组运算符

| Python 表达式                   | 结果                           | 描述     |
| ---------------------------- | ---------------------------- | ------ |
| len((1, 2, 3))               | 3                            | 计算元素个数 |
| (1, 2, 3) + (4, 5, 6)        | (1, 2, 3, 4, 5, 6)           | 连接     |
| ('Hi!',) \* 4                | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | 复制     |
| 3 in (1, 2, 3)               | True                         | 元素是否存在 |
| for x in (1, 2, 3): print x, | 1 2 3                        | 迭代     |

## 2.6 元组内置函数

<table><thead><tr><th width="137">序号</th><th>方法及描述</th></tr></thead><tbody><tr><td>1</td><td><a href="https://www.runoob.com/python/att-tuple-cmp.html">cmp(tuple1, tuple2)</a><br>比较两个元组元素。</td></tr><tr><td>2</td><td><a href="https://www.runoob.com/python/att-tuple-len.html">len(tuple)</a><br>计算元组元素个数。</td></tr><tr><td>3</td><td><a href="https://www.runoob.com/python/att-tuple-max.html">max(tuple)</a><br>返回元组中元素最大值。</td></tr><tr><td>4</td><td><a href="https://www.runoob.com/python/att-tuple-min.html">min(tuple)</a><br>返回元组中元素最小值。</td></tr><tr><td>5</td><td><a href="https://www.runoob.com/python/att-tuple-tuple.html">tuple(seq)</a><br>将列表转换为元组。</td></tr></tbody></table>

