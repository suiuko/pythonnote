# list 列表

## 1.1 列表的定义

`list` 列表再其他语言中通常叫做 数组

列表用 `[]` 定义，数据之间用 `,` 分隔

列表的索引值是从0开始

```python
# 一些用法
len(列表) 获取列表的长度 n+1 
列表.count(数据) 数据在列表中出现的次数
列表.sort()  # 升序排序
列表.sort(reverse = True)  #降序排序
列表.reverse()  # 反转
```

```python
# 定义
name_list =["zhangsan","lisi","wangwu"]
```

## 1.2 列表的基本操作

<table><thead><tr><th width="115">分类</th><th width="189">关键词/函数/方法</th><th>说明</th></tr></thead><tbody><tr><td>1增加 </td><td>list.insert(索引,数据)</td><td>在指定位置插入数据</td></tr><tr><td></td><td>list.append(数据)</td><td>在末尾追加数据</td></tr><tr><td></td><td>list.extend(list2)</td><td>在列表2 的数据追加到列表</td></tr><tr><td>2修改</td><td>list[索引] = 数据</td><td>修改指定索引的数据</td></tr><tr><td>3删除</td><td>del list[索引]</td><td>删除指定索引的数据</td></tr><tr><td></td><td>list.remove[数据]</td><td>删除第一个出现的指定数据</td></tr><tr><td></td><td>list.pop</td><td>删除末尾数据</td></tr><tr><td></td><td>list.pop(索引)</td><td>删除指定索引数据</td></tr><tr><td></td><td>list.clear</td><td>清空列表</td></tr><tr><td>4统计</td><td>len(list)</td><td>列表长度</td></tr><tr><td></td><td>list.count(数据)</td><td>数据在列表中出现的次数</td></tr><tr><td>5排序</td><td>list.sort(cmp = None, key=None,reverse =False)</td><td><p>cpm -- 可选参数，指定该参数会使用该参数的方法进行排序。<br>key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。</p><p>reverse -- 排序规则， true降序，false升序（默认）</p></td></tr><tr><td></td><td>list.sort(reverse=True)</td><td>降序排序</td></tr><tr><td></td><td>list.reverse()</td><td>反转</td></tr><tr><td>6 比较</td><td>cmp(list1,list2)</td><td>比较两个列表的元素</td></tr><tr><td>7 查找</td><td>list.index(obj)</td><td>从列表中找出某个值第一个匹配项的索引位置</td></tr></tbody></table>

```python
name_list = ["zhangsan","lisi","wangwu"]

# 1. 取值、索引、 访问
print(name_list[2])

#知道数据内容，想知道数据在列表中的位置
print(name_list.index("lisi"))

# 访问
print("list[1:3]",name_list[1:3])

# 2. 修改

name_list[1] = "李四"
print(name_list)

# 3. 增加

# append 在列表末尾添加数据
name_list.append("王小二")

# insert 方法在列表的置顶索引位置插入数据
name_list.insert(1,"小明")

# extend 插入整个列表
temp_list = ["孙悟空","猪八戒"]
name_list.extend(temp_list)

print(name_list)
# 4. 删除

# remove 删除指定数据
name_list.remove("wangwu")

# pop 默认把列表最后一个元素删了
name_list.pop()
# pop 可以删指定索引
name_list.pop(4)

# clear 清空列表
name_list.clear()

# delete 本质上是用来将一个变量从内存中删除的

del name_list[1]

name = "小明"
del name # 如果使用del 关键词将变量从内存中删除，后续就不能使用此变量
print(name_list)
```

```python
# 列表的数据统计

name_list = ["zhangsan","lisi","wangwu","wangxiaoer"]

# len(length 长度) 函数 可以统计列表中元素的总数

list_len = len(name_list)
print("列表中包含 %d 个元素" % list_len)

# count 方法可以统计列表中某一个元素出现的次数
count = name_list.count("zhangsan")
print("zhangsan 出现了 %d 次" %count)

# remove 删除元素，多个的话删除左边第一个
name_list.remove("wangwu")
```

#### 列表排序

```python
# 升序 降序

name_list = ["zhang","wang","li"]
num_list = [6,8,1,4,10]

# 升序
name_list.sort()
num_list.sort()

# 降序
name_list.sort(reverse=True)
num_list.sort(reverse=True)

# 逆序（反转）

name_list.reverse()
num_list.reverse()

print(name_list)
print(num_list)
```

## 1.3 循环遍历

遍历就是从头到尾 依次 从 列表中获取数据

在循环体内部 针对 每个元素， 执行相同操作

### 1.3.1 for 循环

```python
# for 循环内部使用的变量 in 列表
for name in name_list:
    循环内部针对列表元素进行操作
    print(name)
```

通过 迭代便利，在循环体内部，针对列表内的元素，执行相同的操作

### 1.3.2 while

```python
list 
i=0
while i < len(list)
```
