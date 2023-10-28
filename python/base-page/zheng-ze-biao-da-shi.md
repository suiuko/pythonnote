# 正则表达式

## re.match函数

re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match() 就返回 none。

```python
re.match(pattern, string, flags=0)
```

<table><thead><tr><th width="159">参数</th><th>描述</th></tr></thead><tbody><tr><td>pattern</td><td>匹配的正则表达式</td></tr><tr><td>string</td><td>要匹配的字符串。</td></tr><tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="https://www.runoob.com/python/python-reg-expressions.html#flags">正则表达式修饰符 - 可选标志</a></td></tr></tbody></table>

我们可以使用 group(num) 或 groups() 匹配对象函数来获取匹配表达式。

<table><thead><tr><th width="227">匹配对象方法</th><th>描述</th></tr></thead><tbody><tr><td>group(num=0)</td><td>匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。</td></tr><tr><td>groups()</td><td>返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。</td></tr></tbody></table>

```python
import re
print(re.match('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.match('com', 'www.runoob.com'))         # 不在起始位置匹配
```

## re.search方法

re.search 扫描整个字符串并返回第一个成功的匹配。

```python
re.search(pattern, string, flags=0)
```

<table><thead><tr><th width="254">参数</th><th>描述</th></tr></thead><tbody><tr><td>pattern</td><td>匹配的正则表达式</td></tr><tr><td>string</td><td>要匹配的字符串。</td></tr><tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。</td></tr></tbody></table>

匹配成功re.search方法返回一个匹配的对象，否则返回None。

我们可以使用group(num) 或 groups() 匹配对象函数来获取匹配表达式。

<table><thead><tr><th width="259">匹配对象方法</th><th>描述</th></tr></thead><tbody><tr><td>group(num=0)</td><td>匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。</td></tr><tr><td>groups()</td><td>返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。</td></tr></tbody></table>

## 检索和替换

```python
re.sub(pattern, repl, string, count=0, flags=0)
```

* pattern : 正则中的模式字符串。
* repl : 替换的字符串，也可为一个函数。
* string : 要被查找替换的原始字符串。
* count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配

### repl 参数是一个函数

以下实例中将字符串中的匹配的数字乘以 2：

```python
import re
 
# 将匹配的数字乘以 2
def double(matched):
    value = int(matched.group('value'))
    return str(value * 2)
 
s = 'A23G4HFD567'
print(re.sub('(?P<value>\d+)', double, s))
```

## re.compile函数

compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。

```python
re.compile(pattern[, flags])
```

参数：

* pattern : 一个字符串形式的正则表达式
* flags : 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：
  1. **re.I** 忽略大小写
  2. **re.L** 表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境
  3. **re.M** 多行模式
  4. **re.S** 即为 . 并且包括换行符在内的任意字符（. 不包括换行符）
  5. **re.U** 表示特殊字符集 \w, \W, \b, \B, \d, \D, \s, \S 依赖于 Unicode 字符属性数据库
  6. **re.X** 为了增加可读性，忽略空格和 # 后面的注释

