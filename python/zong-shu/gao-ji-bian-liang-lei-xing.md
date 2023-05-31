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

