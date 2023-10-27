# tuple 元组

元组中只包含一个元素时，需要在元素后面添加逗号

元组与字符串类似，下标索引从0开始，可以进行截取，组合等。

## 访问元组

元组可以使用下标索引来访问元组中的值。

```python
tup1 = ('physics', 'chemistry', 1997, 2000)
print "tup1[0]: ", tup1[0]
```

## 修改元组

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合。

```python
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')

tup3 = tup1 + tup2
print tup3
>>> (12, 34.56, 'abc', 'xyz')
```

## 元组运算符

| Python 表达式                   | 结果                           | 描述     |
| ---------------------------- | ---------------------------- | ------ |
| len((1, 2, 3))               | 3                            | 计算元素个数 |
| (1, 2, 3) + (4, 5, 6)        | (1, 2, 3, 4, 5, 6)           | 连接     |
| ('Hi!',) \* 4                | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | 复制     |
| 3 in (1, 2, 3)               | True                         | 元素是否存在 |
| for x in (1, 2, 3): print x, | 1 2 3                        | 迭代     |

## 元组内置函数

<table><thead><tr><th width="137">序号</th><th>方法及描述</th></tr></thead><tbody><tr><td>1</td><td><a href="https://www.runoob.com/python/att-tuple-cmp.html">cmp(tuple1, tuple2)</a><br>比较两个元组元素。</td></tr><tr><td>2</td><td><a href="https://www.runoob.com/python/att-tuple-len.html">len(tuple)</a><br>计算元组元素个数。</td></tr><tr><td>3</td><td><a href="https://www.runoob.com/python/att-tuple-max.html">max(tuple)</a><br>返回元组中元素最大值。</td></tr><tr><td>4</td><td><a href="https://www.runoob.com/python/att-tuple-min.html">min(tuple)</a><br>返回元组中元素最小值。</td></tr><tr><td>5</td><td><a href="https://www.runoob.com/python/att-tuple-tuple.html">tuple(seq)</a><br>将列表转换为元组。</td></tr></tbody></table>
