# 运算符

别的太简单了

{% embed url="https://www.runoob.com/python/python-operators.html#ysf2" %}

## 位运算符 <a href="#ysf5" id="ysf5"></a>

按位运算符是把数字看作二进制来进行计算的。

```python
a = 0011 1100

b = 0000 1101

-----------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011

```

<table><thead><tr><th width="121.33333333333331">运算符</th><th>描述</th><th>实例</th></tr></thead><tbody><tr><td>&#x26;</td><td>按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0</td><td>(a &#x26; b) 输出结果 12 ，二进制解释： 0000 1100</td></tr><tr><td>|</td><td>按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。</td><td>(a | b) 输出结果 61 ，二进制解释： 0011 1101</td></tr><tr><td>^</td><td>按位异或运算符：当两对应的二进位相异时，结果为1</td><td>(a ^ b) 输出结果 49 ，二进制解释： 0011 0001</td></tr><tr><td>~</td><td>按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1 。~x 类似于 -x-1</td><td>(~a ) 输出结果 -61 ，二进制解释： 1100 0011，在一个有符号二进制数的补码形式。</td></tr><tr><td>&#x3C;&#x3C;</td><td>左移动运算符：运算数的各二进位全部左移若干位，由 &#x3C;&#x3C; 右边的数字指定了移动的位数，高位丢弃，低位补0。</td><td>a &#x3C;&#x3C; 2 输出结果 240 ，二进制解释： 1111 0000</td></tr><tr><td>>></td><td>右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，>> 右边的数字指定了移动的位数</td><td>a >> 2 输出结果 15 ，二进制解释： 0000 1111</td></tr></tbody></table>

## 逻辑运算符 <a href="#ysf4" id="ysf4"></a>

Python语言支持逻辑运算符，以下假设变量 a 为 10, b为 20:

<table><thead><tr><th width="153">运算符</th><th width="135">逻辑表达式</th><th>描述</th><th>实例</th></tr></thead><tbody><tr><td>and</td><td>x and y</td><td>布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。</td><td>(a and b) 返回 20。</td></tr><tr><td>or</td><td>x or y</td><td>布尔"或" - 如果 x 是非 0，它返回 x 的计算值，否则它返回 y 的计算值。</td><td>(a or b) 返回 10。</td></tr><tr><td>not</td><td>not x</td><td>布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。</td><td>not(a and b) 返回 False</td></tr></tbody></table>

## 成员运算符 <a href="#ysf6" id="ysf6"></a>

除了以上的一些运算符之外，Python还支持成员运算符，测试实例中包含了一系列的成员，包括字符串，列表或元组。

<table><thead><tr><th width="147.33333333333331">运算符</th><th>描述</th><th>实例</th></tr></thead><tbody><tr><td>in</td><td>如果在指定的序列中找到值返回 True，否则返回 False。</td><td>x 在 y 序列中 , 如果 x 在 y 序列中返回 True。</td></tr><tr><td>not in</td><td>如果在指定的序列中没有找到值返回 True，否则返回 False。</td><td>x 不在 y 序列中 , 如果 x 不在 y 序列中返回 True。</td></tr></tbody></table>

## 身份运算符 <a href="#ysf7" id="ysf7"></a>

身份运算符用于比较两个对象的存储单元

<table><thead><tr><th width="135.33333333333331">运算符</th><th>描述</th><th>实例</th></tr></thead><tbody><tr><td>is</td><td>is 是判断两个标识符是不是引用自一个对象</td><td><strong>x is y</strong>, 类似 <strong>id(x) == id(y)</strong> , 如果引用的是同一个对象则返回 True，否则返回 False</td></tr><tr><td>is not</td><td>is not 是判断两个标识符是不是引用自不同对象</td><td><strong>x is not y</strong> ， 类似 <strong>id(a) != id(b)</strong>。如果引用的不是同一个对象则返回结果 True，否则返回 False。</td></tr></tbody></table>

## 运算符优先级

<table><thead><tr><th width="260">运算符</th><th>描述</th></tr></thead><tbody><tr><td>**</td><td>指数 (最高优先级)</td></tr><tr><td>~ + -</td><td>按位翻转, 一元加号和减号 (最后两个的方法名为 +@ 和 -@)</td></tr><tr><td>* / % //</td><td>乘，除，取模和取整除</td></tr><tr><td>+ -</td><td>加法减法</td></tr><tr><td>>> &#x3C;&#x3C;</td><td>右移，左移运算符</td></tr><tr><td>&#x26;</td><td>位 'AND'</td></tr><tr><td>^ |</td><td>位运算符</td></tr><tr><td>&#x3C;= &#x3C; > >=</td><td>比较运算符</td></tr><tr><td>&#x3C;> == !=</td><td>等于运算符</td></tr><tr><td>= %= /= //= -= += *= **=</td><td>赋值运算符</td></tr><tr><td>is is not</td><td>身份运算符</td></tr><tr><td>in not in</td><td>成员运算符</td></tr><tr><td>not and or</td><td>逻辑运算符</td></tr></tbody></table>

