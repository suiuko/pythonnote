# 高级变量类型

## 目标

* 列表
* 元组
* 字典
* 字符串
* 公共方法
* 变量高级

## 知识点回顾

### 数据类型

数字型和非数字型

#### 数字型

| 类型  | 描述      |
| --- | ------- |
| 整型  | int     |
| 浮点型 | float   |
| 布尔型 | bool    |
| 复合型 | complex |

#### 非数字型

| 类型  | 描述 |
| --- | -- |
| 字符串 |    |
| 列表  |    |
| 元组  |    |
| 字典  |    |

所有非数字型变量都支持一下特点

* 都是一个序列 `sequence` 也可以理解为容器
* 取值`[ ]`
* 遍历 `for in`
* 计算长度、最大/最小值、比较、删除
* 链接 `+` 和重复 `*`&#x20;
* 切片

## 1. 列表

### 1.1 列表的定义

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

### 1.2 列表的基本操作

<table><thead><tr><th width="115">分类</th><th width="189">关键词/函数/方法</th><th>说明</th></tr></thead><tbody><tr><td>1增加 </td><td>list.insert(索引,数据)</td><td>在指定位置插入数据</td></tr><tr><td></td><td>list.append(数据)</td><td>在末尾追加数据</td></tr><tr><td></td><td>list.extend(list2)</td><td>在列表2 的数据追加到列表</td></tr><tr><td>2修改</td><td>list[索引] = 数据</td><td>修改指定索引的数据</td></tr><tr><td>3删除</td><td>del list[索引]</td><td>删除指定索引的数据</td></tr><tr><td></td><td>list.remove[数据]</td><td>删除第一个出现的指定数据</td></tr><tr><td></td><td>list.pop</td><td>删除末尾数据</td></tr><tr><td></td><td>list.pop(索引)</td><td>删除指定索引数据</td></tr><tr><td></td><td>list.clear</td><td>清空列表</td></tr><tr><td>4统计</td><td>len(list)</td><td>列表长度</td></tr><tr><td></td><td>list.count(数据)</td><td>数据在列表中出现的次数</td></tr><tr><td>5排序</td><td>list.sort()</td><td>升序排序</td></tr><tr><td></td><td>list.sort(reverse=True)</td><td>降序排序</td></tr><tr><td></td><td>list.reverse()</td><td>反转</td></tr></tbody></table>

```python
name_list = ["zhangsan","lisi","wangwu"]

# 1. 取值和索引
print(name_list[2])

#知道数据内容，想知道数据在列表中的位置
print(name_list.index("lisi"))

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

#### 关键字、函数和方法

关键字是python 内置的、具有特殊意义的标识符

> 关键字后面不需要使用括号

函数封装了独立功能，可以直接调用

> 函数名(参数) ，函数需要死记硬背

方法类似于函数，但是方法需要通过 对象 来调用，表示针对这个 对象 要做的操作

> 对象.方法名(参数)  ； 在变量后面输入 `.` 然后选择这个变量要执行的操作

### 1.3 循环遍历

遍历就是从头到尾 依次 从 列表中获取数据

在循环体内部 针对 每个元素， 执行相同操作

#### 1.3.1 for 循环

```python
# for 循环内部使用的变量 in 列表
for name in name_list:
    循环内部针对列表元素进行操作
    print(name)
```

通过 迭代便利，在循环体内部，针对列表内的元素，执行相同的操作



