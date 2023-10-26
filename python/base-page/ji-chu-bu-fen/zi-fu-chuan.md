# 字符串

使用引号 ( ' 或 " ) 来创建字符串。

## 访问字符串中的值

Python 不支持单字符类型，单字符在 Python 中也是作为一个字符串使用。

Python 访问子字符串，可以使用方括号来截取字符串，如下实例：

```python
var1 = 'hello world!'

print ("va1[0]:", var1[0])
```

## 几种遍历字符串的方法

```python
var1 = 'hello world!'
# 1. --------通过数组+range遍历
print ("va1[0]:", var1[0])
for i in range(len(var1)):
   print(var1[i],end="")

# 2. --------通过列表遍历
lst = list(var1)
for i in lst:
   print(i,end="")
print(end="\n")

# 3. ---------直接遍历
for c in var1:
   print(c,end="")
print(end="\n")

# 4.  使用 while 遍历
i = 0
while i < len(var1):
   print(var1[i],end="")
   i += 1
print("\n")

# 5. 切片遍历
for c in var1[::2]:
   print(c)
```

## 转义字符

<table><thead><tr><th width="243">转义字符</th><th>描述</th></tr></thead><tbody><tr><td>\(在行尾时)</td><td>续行符</td></tr><tr><td>\\</td><td>反斜杠符号</td></tr><tr><td>\'</td><td>单引号</td></tr><tr><td>\"</td><td>双引号</td></tr><tr><td>\a</td><td>响铃</td></tr><tr><td>\b</td><td>退格(Backspace)</td></tr><tr><td>\e</td><td>转义</td></tr><tr><td>\000</td><td>空</td></tr><tr><td>'\n'</td><td>换行</td></tr><tr><td>\v</td><td>纵向制表符</td></tr><tr><td>'\t'</td><td>横向制表符</td></tr><tr><td>'\r'</td><td>回车</td></tr><tr><td>\f</td><td>换页</td></tr><tr><td>\oyy</td><td>八进制数，y 代表 0~7 的字符，例如：\012 代表换行。</td></tr><tr><td>\xyy</td><td>十六进制数，以 \x 开头，yy代表的字符，例如：\x0a代表换行</td></tr><tr><td>\other</td><td>其它的字符以普通格式输出</td></tr></tbody></table>

## 字符串运算符

<table data-header-hidden><thead><tr><th width="143.33333333333331"></th><th></th><th></th></tr></thead><tbody><tr><td>+</td><td>字符串连接</td><td>>>>a + b 'HelloPython'</td></tr><tr><td>*</td><td>重复输出字符串</td><td>>>>a * 2 'HelloHello'</td></tr><tr><td>[]</td><td>通过索引获取字符串中字符</td><td>>>>a[1] 'e'</td></tr><tr><td>[ : ]</td><td>截取字符串中的一部分</td><td>>>>a[1:4] 'ell'</td></tr><tr><td>in</td><td>成员运算符 - 如果字符串中包含给定的字符返回 True</td><td>>>>"H" in a True</td></tr><tr><td>not in</td><td>成员运算符 - 如果字符串中不包含给定的字符返回 True</td><td>>>>"M" not in a True</td></tr><tr><td>r/R</td><td>原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前加上字母"r"（可以大小写）以外，与普通字符串有着几乎完全相同的语法。</td><td>>>>print r'' \n >>> print R'' \n</td></tr><tr><td>%</td><td>格式字符串</td><td>请看字符串格式化</td></tr></tbody></table>

## 字符串格式化

```python
print "My name is %s and weight is %d kg!" % ('Zara', 21) 

>>> My name is Zara and weight is 21 kg!
```

python 字符串格式化符号:

<table><thead><tr><th width="199">符   号</th><th>描述</th></tr></thead><tbody><tr><td>      %c</td><td> 格式化字符及其ASCII码</td></tr><tr><td>      %s</td><td> 格式化字符串</td></tr><tr><td>      %d</td><td> 格式化整数</td></tr><tr><td>      %u</td><td> 格式化无符号整型</td></tr><tr><td>      %o</td><td> 格式化无符号八进制数</td></tr><tr><td>      %x</td><td> 格式化无符号十六进制数</td></tr><tr><td>      %X</td><td> 格式化无符号十六进制数（大写）</td></tr><tr><td>      %f</td><td> 格式化浮点数字，可指定小数点后的精度</td></tr><tr><td>      %e</td><td> 用科学计数法格式化浮点数</td></tr><tr><td>      %E</td><td> 作用同%e，用科学计数法格式化浮点数</td></tr><tr><td>      %g</td><td> %f和%e的简写</td></tr><tr><td>      %G</td><td> %F 和 %E 的简写</td></tr><tr><td>      %p</td><td> 用十六进制数格式化变量的地址</td></tr></tbody></table>

格式化操作符辅助指令:

<table><thead><tr><th width="220">符号</th><th>功能</th></tr></thead><tbody><tr><td>*</td><td>定义宽度或者小数点精度</td></tr><tr><td>-</td><td>用做左对齐</td></tr><tr><td>+</td><td>在正数前面显示加号( + )</td></tr><tr><td>&#x3C;sp></td><td>在正数前面显示空格</td></tr><tr><td>#</td><td>在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X')</td></tr><tr><td>0</td><td>显示的数字前面填充'0'而不是默认的空格</td></tr><tr><td>%</td><td>'%%'输出一个单一的'%'</td></tr><tr><td>(var)</td><td>映射变量(字典参数)</td></tr><tr><td>m.n.</td><td>m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)</td></tr></tbody></table>

## 字符串内建函数

| 方法                                                                                                               | 描述                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [string.capitalize()](https://www.runoob.com/python/att-string-capitalize.html)                                  | 把字符串的第一个字符大写                                                                                                                                                        |
| [string.center(width)](https://www.runoob.com/python/att-string-center.html)                                     | 返回一个原字符串居中,并使用空格填充至长度 width 的新字符串                                                                                                                                   |
| [**string.count(str, beg=0, end=len(string))**](https://www.runoob.com/python/att-string-count.html)             | 返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数                                                                                                          |
| [string.decode(encoding='UTF-8', errors='strict')](https://www.runoob.com/python/att-string-decode.html)         | 以 encoding 指定的编码格式解码 string，如果出错默认报一个 ValueError 的 异 常 ， 除非 errors 指 定 的 是 'ignore' 或 者'replace'                                                                    |
| [string.encode(encoding='UTF-8', errors='strict')](https://www.runoob.com/python/att-string-encode.html)         | 以 encoding 指定的编码格式编码 string，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'                                                                               |
| [**string.endswith(obj, beg=0, end=len(string))**](https://www.runoob.com/python/att-string-endswith.html)       | 检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内是否以 obj 结束，如果是，返回 True,否则返回 False.                                                                                          |
| [string.expandtabs(tabsize=8)](https://www.runoob.com/python/att-string-expandtabs.html)                         | 把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8。                                                                                                                          |
| [**string.find(str, beg=0, end=len(string))**](https://www.runoob.com/python/att-string-find.html)               | 检测 str 是否包含在 string 中，如果 beg 和 end 指定范围，则检查是否包含在指定范围内，如果是返回开始的索引值，否则返回-1                                                                                            |
| [**string.format()**](https://www.runoob.com/python/att-string-format.html)                                      | 格式化字符串                                                                                                                                                              |
| [**string.index(str, beg=0, end=len(string))**](https://www.runoob.com/python/att-string-index.html)             | 跟find()方法一样，只不过如果str不在 string中会报一个异常.                                                                                                                               |
| [string.isalnum()](https://www.runoob.com/python/att-string-isalnum.html)                                        | <p>如果 string 至少有一个字符并且所有字符都是字母或数字则返</p><p>回 True,否则返回 False</p>                                                                                                     |
| [string.isalpha()](https://www.runoob.com/python/att-string-isalpha.html)                                        | <p>如果 string 至少有一个字符并且所有字符都是字母则返回 True,</p><p>否则返回 False</p>                                                                                                        |
| [string.isdecimal()](https://www.runoob.com/python/att-string-isdecimal.html)                                    | 如果 string 只包含十进制数字则返回 True 否则返回 False.                                                                                                                              |
| [string.isdigit()](https://www.runoob.com/python/att-string-isdigit.html)                                        | 如果 string 只包含数字则返回 True 否则返回 False.                                                                                                                                 |
| [string.islower()](https://www.runoob.com/python/att-string-islower.html)                                        | 如果 string 中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False                                                                                                  |
| [string.isnumeric()](https://www.runoob.com/python/att-string-isnumeric.html)                                    | 如果 string 中只包含数字字符，则返回 True，否则返回 False                                                                                                                              |
| [string.isspace()](https://www.runoob.com/python/att-string-isspace.html)                                        | 如果 string 中只包含空格，则返回 True，否则返回 False.                                                                                                                               |
| [string.istitle()](https://www.runoob.com/python/att-string-istitle.html)                                        | 如果 string 是标题化的(见 title())则返回 True，否则返回 False                                                                                                                       |
| [string.isupper()](https://www.runoob.com/python/att-string-isupper.html)                                        | 如果 string 中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False                                                                                                  |
| [**string.join(seq)**](https://www.runoob.com/python/att-string-join.html)                                       | 以 string 作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串                                                                                                                       |
| [string.ljust(width)](https://www.runoob.com/python/att-string-ljust.html)                                       | 返回一个原字符串左对齐,并使用空格填充至长度 width 的新字符串                                                                                                                                  |
| [string.lower()](https://www.runoob.com/python/att-string-lower.html)                                            | 转换 string 中所有大写字符为小写.                                                                                                                                               |
| [string.lstrip()](https://www.runoob.com/python/att-string-lstrip.html)                                          | 截掉 string 左边的空格                                                                                                                                                     |
| [string.maketrans(intab, outtab)](https://www.runoob.com/python/att-string-maketrans.html)                       | maketrans() 方法用于创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。                                                                                 |
| [max(str)](https://www.runoob.com/python/att-string-max.html)                                                    | 返回字符串 _str_ 中最大的字母。                                                                                                                                                 |
| [min(str)](https://www.runoob.com/python/att-string-min.html)                                                    | 返回字符串 _str_ 中最小的字母。                                                                                                                                                 |
| [**string.partition(str)**](https://www.runoob.com/python/att-string-partition.html)                             | 有点像 find()和 split()的结合体,从 str 出现的第一个位置起,把 字 符 串 string 分 成 一 个 3 元 素 的 元 组 (string\_pre\_str,str,string\_post\_str),如果 string 中不包含str 则 string\_pre\_str == string. |
| [**string.replace(str1, str2,  num=string.count(str1))**](https://www.runoob.com/python/att-string-replace.html) | 把 string 中的 str1 替换成 str2,如果 num 指定，则替换不超过 num 次.                                                                                                                   |
| [string.rfind(str, beg=0,end=len(string) )](https://www.runoob.com/python/att-string-rfind.html)                 | 类似于 find() 函数，返回字符串最后一次出现的位置，如果没有匹配项则返回 -1。                                                                                                                         |
| [string.rindex( str, beg=0,end=len(string))](https://www.runoob.com/python/att-string-rindex.html)               | 类似于 index()，不过是返回最后一个匹配到的子字符串的索引号。                                                                                                                                  |
| [string.rjust(width)](https://www.runoob.com/python/att-string-rjust.html)                                       | 返回一个原字符串右对齐,并使用空格填充至长度 width 的新字符串                                                                                                                                  |
| [string.rpartition(str)](https://www.runoob.com/python/att-string-rpartition.html)                               | 类似于 partition()函数,不过是从右边开始查找                                                                                                                                        |
| [string.rstrip()](https://www.runoob.com/python/att-string-rstrip.html)                                          | 删除 string 字符串末尾的空格.                                                                                                                                                 |
| [**string.split(str="", num=string.count(str))**](https://www.runoob.com/python/att-string-split.html)           | 以 str 为分隔符切片 string，如果 num 有指定值，则仅分隔 **num+1** 个子字符串                                                                                                                |
| [string.splitlines(\[keepends\])](https://www.runoob.com/python/att-string-splitlines.html)                      | 按照行('\r', '\r\n', '\n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。                                                                             |
| [string.startswith(obj, beg=0,end=len(string))](https://www.runoob.com/python/att-string-startswith.html)        | 检查字符串是否是以 obj 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查.                                                                                                    |
| [**string.strip(\[obj\])**](https://www.runoob.com/python/att-string-strip.html)                                 | 在 string 上执行 lstrip()和 rstrip()                                                                                                                                     |
| [string.swapcase()](https://www.runoob.com/python/att-string-swapcase.html)                                      | 翻转 string 中的大小写                                                                                                                                                     |
| [string.title()](https://www.runoob.com/python/att-string-title.html)                                            | 返回"标题化"的 string,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle())                                                                                                                |
| [**string.translate(str, del="")**](https://www.runoob.com/python/att-string-translate.html)                     | <p>根据 str 给出的表(包含 256 个字符)转换 string 的字符,</p><p>要过滤掉的字符放到 del 参数中</p>                                                                                                |
| [string.upper()](https://www.runoob.com/python/att-string-upper.html)                                            | 转换 string 中的小写字母为大写                                                                                                                                                 |
| [string.zfill(width)](https://www.runoob.com/python/att-string-zfill.html)                                       | 返回长度为 width 的字符串，原字符串 string 右对齐，前面填充0                                                                                                                              |

```python

hello_str = "hello,world"

# 1. 判断是否以特定字符串开始

print(hello_str.startswith("hello"))
>>> True
# 2. 判断是否以特定字符串结束

print(hello_str.endswith("world"))
>>> True
# 3. 查找指定字符串
# index同样可以查找指定的字符串在打字符串中的索引
print(hello_str.find("llo"))   #输出2，字符串不存在会报错

print(hello_str.index("llo"))  # 字符串不存在会输出-1

# 4. 替换字符串
# replace 执行完成后 会返回一个新的字符串
# 注意： 不会修改原有字符串的内容
print(hello_str.replace("world","python"))
print(hello_str)
```
