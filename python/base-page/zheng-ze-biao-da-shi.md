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

在上面，当匹配成功时返回一个 match 对象

* `group([group1, …])` 方法用于获得一个或多个分组匹配的字符串，当要获得整个匹配的子串时，可直接使用 `group()` 或 `group(0)`；
* `start([group])` 方法用于获取分组匹配的子串在整个字符串中的起始位置（子串第一个字符的索引），参数默认值为 0；
* `end([group])` 方法用于获取分组匹配的子串在整个字符串中的结束位置（子串最后一个字符的索引+1），参数默认值为 0；
* `span([group])` 方法返回 `(start(group), end(group))`

## findall&#x20;

在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果有多个匹配模式，则返回元组列表，如果没有找到匹配的，则返回空列表。

**注意：** match 和 search 是匹配一次 findall 匹配所有。

```python
findall(string[, pos[, endpos]])
```

## re.finditer

和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。

```python
re.finditer(pattern, string, flags=0)
```

<table><thead><tr><th width="227">参数</th><th>描述</th></tr></thead><tbody><tr><td>pattern</td><td>匹配的正则表达式</td></tr><tr><td>string</td><td>要匹配的字符串。</td></tr><tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="https://www.runoob.com/python/python-reg-expressions.html#flags">正则表达式修饰符 - 可选标志</a></td></tr></tbody></table>

## re.split

split 方法按照能够匹配的子串将字符串分割后返回列表，它的使用形式如下：

```python
re.split(pattern, string[, maxsplit=0, flags=0])
```

<table><thead><tr><th width="184">参数</th><th>描述</th></tr></thead><tbody><tr><td>pattern</td><td>匹配的正则表达式</td></tr><tr><td>string</td><td>要匹配的字符串。</td></tr><tr><td>maxsplit</td><td>分隔次数，maxsplit=1 分隔一次，默认为 0，不限制次数。</td></tr><tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="https://www.runoob.com/python/python-reg-expressions.html#flags">正则表达式修饰符 - 可选标志</a></td></tr></tbody></table>

## 正则表达式对象

#### re.RegexObject

re.compile() 返回 RegexObject 对象。

#### re.MatchObject

group() 返回被 RE 匹配的字符串。

* start() 返回匹配开始的位置
* end() 返回匹配结束的位置
* span() 返回一个元组包含匹配 (开始,结束) 的位置

## 正则表达式修饰符

<table><thead><tr><th width="175">修饰符</th><th>描述</th></tr></thead><tbody><tr><td>re.I</td><td>使匹配对大小写不敏感</td></tr><tr><td>re.L</td><td>做本地化识别（locale-aware）匹配</td></tr><tr><td>re.M</td><td>多行匹配，影响 ^ 和 $</td></tr><tr><td>re.S</td><td>使 . 匹配包括换行在内的所有字符</td></tr><tr><td>re.U</td><td>根据Unicode字符集解析字符。这个标志影响 \w, \W, \b, \B.</td></tr><tr><td>re.X</td><td>该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。</td></tr></tbody></table>

## 正则表达式模式

<table><thead><tr><th width="170">模式</th><th>描述</th></tr></thead><tbody><tr><td>^</td><td>匹配字符串的开头</td></tr><tr><td>$</td><td>匹配字符串的末尾。</td></tr><tr><td>.</td><td>匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。</td></tr><tr><td>[...]</td><td>用来表示一组字符,单独列出：[amk] 匹配 'a'，'m'或'k'</td></tr><tr><td>[^...]</td><td>不在[]中的字符：[^abc] 匹配除了a,b,c之外的字符。</td></tr><tr><td>re*</td><td>匹配0个或多个的表达式。</td></tr><tr><td>re+</td><td>匹配1个或多个的表达式。</td></tr><tr><td>re?</td><td>匹配0个或1个由前面的正则表达式定义的片段，非贪婪方式</td></tr><tr><td>re{ n}</td><td>精确匹配 n 个前面表达式。例如， o{2} 不能匹配 "Bob" 中的 "o"，但是能匹配 "food" 中的两个 o。</td></tr><tr><td>re{ n,}</td><td>匹配 n 个前面表达式。例如， o{2,} 不能匹配"Bob"中的"o"，但能匹配 "foooood"中的所有 o。"o{1,}" 等价于 "o+"。"o{0,}" 则等价于 "o*"。</td></tr><tr><td>re{ n, m}</td><td>匹配 n 到 m 次由前面的正则表达式定义的片段，贪婪方式</td></tr><tr><td>a| b</td><td>匹配a或b</td></tr><tr><td>(re)</td><td>对正则表达式分组并记住匹配的文本</td></tr><tr><td>(?P..)</td><td><p>分组匹配，转为字典模式，方便使用</p><pre><code>s = '1102231990xxxxxxxx'
res = re.search('(?P&#x3C;province>\d{3})(?P&#x3C;city>\d{3})(?P&#x3C;born_year>\d{4})',s)

>>> {'province': '110', 'city': '223', 'born_year': '1990'} 
</code></pre></td></tr><tr><td>(?imx)</td><td>正则表达式包含三种可选标志：i, m, 或 x 。只影响括号中的区域。</td></tr><tr><td>(?-imx)</td><td>正则表达式关闭 i, m, 或 x 可选标志。只影响括号中的区域。</td></tr><tr><td>(?: re)</td><td>类似 (...), 但是不表示一个组</td></tr><tr><td>(?imx: re)</td><td>在括号中使用i, m, 或 x 可选标志</td></tr><tr><td>(?-imx: re)</td><td>在括号中不使用i, m, 或 x 可选标志</td></tr><tr><td>(?#...)</td><td>注释.</td></tr><tr><td>(?= re)</td><td>前向肯定界定符。如果所含正则表达式，以 ... 表示，在当前位置成功匹配时成功，否则失败。但一旦所含表达式已经尝试，匹配引擎根本没有提高；模式的剩余部分还要尝试界定符的右边。</td></tr><tr><td>(?! re)</td><td>前向否定界定符。与肯定界定符相反；当所含表达式不能在字符串当前位置匹配时成功</td></tr><tr><td>(?> re)</td><td>匹配的独立模式，省去回溯。</td></tr><tr><td>\w</td><td>匹配字母数字及下划线</td></tr><tr><td>\W</td><td>匹配非字母数字及下划线</td></tr><tr><td>\s</td><td>匹配任意空白字符，等价于 [ \t\n\r\f]。</td></tr><tr><td>\S</td><td>匹配任意非空字符</td></tr><tr><td>\d</td><td>匹配任意数字，等价于 [0-9].</td></tr><tr><td>\D</td><td>匹配任意非数字</td></tr><tr><td>\A</td><td>匹配字符串开始</td></tr><tr><td>\Z</td><td>匹配字符串结束，如果是存在换行，只匹配到换行前的结束字符串。</td></tr><tr><td>\z</td><td>匹配字符串结束</td></tr><tr><td>\G</td><td>匹配最后匹配完成的位置。</td></tr><tr><td>\b</td><td>匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。</td></tr><tr><td>\B</td><td>匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。</td></tr><tr><td>\n, \t, 等.</td><td>匹配一个换行符。匹配一个制表符。等</td></tr><tr><td>\1...\9</td><td>匹配第n个分组的内容。</td></tr><tr><td>\10</td><td>匹配第n个分组的内容，如果它经匹配。否则指的是八进制字符码的表达式。</td></tr></tbody></table>
