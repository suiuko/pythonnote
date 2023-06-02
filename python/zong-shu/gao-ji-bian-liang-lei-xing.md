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

## 2 元组

### 2.1 元组的定义

`tuple` （元组） 与 列表类似，不同之处在于 元组的 元素不能修改

元素的索引从`0` 开始，元组用 `()` 来定义

元组表示多个元素组成的序列

### 2.2 元组常用操作

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

### 2.3 循环遍历

取值 就是从 元组 中获取存储在指定位置的数据

遍历 就是 从头到尾 依次 从 元组 中获取数据

```python
# for 循环内部使用的变量 in 元组
for item in info:
    循环内部针对元组元素进行操作
    print(item)
```

`for` 循环遍历所有非数字型类型的变量： 列表、元组、字典、字符串

### 2.4 应用场景

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

## 3 字典

### 3.1 字典的定义

字典是 无序的 对象集合\
列表是 有序的 对象集合

字典用`{}` 定义

字典使用 `键值对` 存储数据，键值对之间用 `,` 分隔

* 键 `key` 是索引
* 值 `value` 是数据
* 键和值 之间使用`:` 分隔
* 键必须是唯一的
* 值可以取任何数据类型，键只能使用字符串、数字、元组

```python
# 定义字典
xiaoming = {"name":"小明",
            "age":18,
            "gender":True,
            "height":1.75}
print(xiaoming)
```

### 3.2.1 字典基本使用

```python
xiaoming_dict = {"name":"小明"}

# 1. 取值
print(xiaoming_dict["name"])

# 2. 增加/修改
# 如果key不存在，会新增键值对
xiaoming_dict["age"] = 18
# 如果key存在，会修改已经存在的键值对
xiaoming_dict["name"] = "小小明"

# 3. 删除
xiaoming_dict.pop("name")

print(xiaoming_dict)
```

### 3.2.2 字典常用操作

|         |      |
| ------- | ---- |
| update  | 合并字典 |
|         |      |
|         |      |

```python
xiaoming_dict = {"name":"小明",
                 "age":18}
# 1. 统计键值对的数量
print(len(xiaoming_dict))

# 2. 合并字典
temp_dict = {"height":1.75}
# 注意：如果被合并的字典中包含已经存在的键值对，会覆盖原有的键值对
xiaoming_dict.update(temp_dict)

# 3. 清空字典
xiaoming_dict.clear()
```

### 3.3 字典循环遍历

```python
# 字典的遍历 
xiaoming_dict = {"name": "xiaoming",
                 "qq":"1234",
                 "phone":"1000"}

# 变量K是 每次循环中，获取到的键值对的key

for k in xiaoming_dict:
    print("%s : %s" %(k,xiaoming_dict[k]))
    
```

### 3.4 应用场景

使用多个键值对，存储描述一个 物体 的相关信息 -- 描述更复杂的数据信息

将 多个字典 放在 一个列表 中，再进行遍历，在循环体内部针对每一个字典进行 相同的处理

可以将 多个 字典 存放在一个 列表 中

```python
card_list = [{"name": "xiaoming",
                 "qq":"1234",
                 "phone":"1000"},
            {
                "name":"lisi",
                "qq":"54321",
                "phone":"1111"}
            ]

for card_info in card_list:
    print(card_info)

# 需要注意的是，字典是无序的对象集合，输出可能顺序不一样
# 但是列表是有序的对象集合
```

## 4 字符串

### 4.1 字符串的定义

字符串就是一串字符，表示文本的数据类型

格式： 使用 一对双引号 `" "` 或者 一对单引号 `' '` 定义一个字符串

> 如果字符串内部需要使用`"` ，可以使用`'` 定义字符串\
> 如果字符串内部需要使用`'` ，可以使用`"` 定义字符串

可以使用 索引 获取一个字符串中 指定位置的字符，索引计数从 0 开始

也可以使用 `for` 循环遍历字符串中每一个字符

```python
string = "hello"
for c in string:
    print(c)


str1 = "hello python"
str2 = "我是大西瓜"

for char in str2:
    print(char)
```

`len(字符串)` 获取字符串的长度\
`字符串.count(字符串)` 获取 小字符串 是第一次出现的索引

### 4.2 字符串常用操作

index方法：某一个子字符串出现的位置； 如果使用此方法传递的子字符串不存在，会报错。

#### 4.2.1 判断类型

| 方法               | 说明                                   |
| ---------------- | ------------------------------------ |
| string.isspace() | 只包含空格，返回true，还可以看空白字符                |
| isalnum          | 如果至少有一个字符并且所有字符都是字母或者数字则返回True       |
| isalpha          | 如果至少有一个字符并且所有字符都是字母则返回True           |
| isdecimal        | 只有数字返回T                              |
| islower          | 至少一个区分大小写的字符，并且所有这些（区分大小写）字符都是小写，返回T |
| isupper          | 至少一个区分大小写的字符，并且所有这些（区分大小写）字符都是大写，返回T |

#### 4.2.2 查找与替换

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

#### 4.2.3 大小写转换

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

#### 4.2.4&#x20;

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

#### 4.2.5&#x20;

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

#### 4.2.6

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |
