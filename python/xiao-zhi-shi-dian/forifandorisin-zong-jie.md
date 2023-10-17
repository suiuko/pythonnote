# for-if-and-or-is-in-==总结

## 一、for、if for：

用于遍历任何序列的项目，如一个列表或者一个字符串 用法： for item in list： 执行语句……

if：

用于判断 用法： if 判断条件： 执行语句…… else： 执行语句……

if 判断条件： 执行语句…… elif： 执行语句…… else： 执行语句……

例如：定义一个列表，遍历列表，如果是ccc，则输出CCC，如果是bbb，则输出Bbb，否则，输出该项：

```python
list = ['aaa', 'bbb', 'ccc', 'ddd']
for item in list:
    if item == 'ccc':
        print(item.upper())
    elif item == 'bbb':
        print(item.title())
    else:
        print(item)
```

## 二、and、or及短路逻辑

&#x20;       [逻辑或](https://so.csdn.net/so/search?q=%E9%80%BB%E8%BE%91%E6%88%96\&spm=1001.2101.3001.7020)：or，也就是其他语言的||，一真即真，全假才假

&#x20;       逻辑与：and，也就是其他语言的&&，全真才真，一假即假

```python
a = 0
b = 1
# 输出0
print(a and b)
# 输出1
print(a or b)
c = a > b or b > 1
# 输出False
print(c)
d = 'hello'
# 输出hello
print(a or d)
# 输出1
print(b or d)
# 输出hello
print(d or b)
# 输出hello
print(c or d)
# 输出False
print(c and d)
```

a and b：a为0，假，and语句，不再往后判断，直接输出a的值0&#x20;

a or b：a为0，假，or语句，继续判断，b为1，真，输出b的值1&#x20;

a or d：a为0，假，or语句，继续判断，d为'hello'，真，输出d的值'hello'&#x20;

b or d：b为1，真，or语句，不再往后判断，直接输出b的值1&#x20;

d or b：d为'hello'，真，or语句，不再往后判断，直接输出d的值'hello'&#x20;

c or d：c为False，假，or语句，继续判断，d为'hello'，真，输出d的值'hello'&#x20;

c and d：c为False，假，and语句，不再往后判断，直接输出c的值False 只对bool表达式进行操作时，返回值是bool类型；

对其他类型运算进行操作时，返回值时其表达式的值。

## 三、is、in、==&#x20;

is：比较两个对象是否指向同一存储单元&#x20;

\==：判断值或内容是否相等&#x20;

in：在指定的序列（列表、范围、字符串等）中找到值，返回True，否则返回False。&#x20;

```python
a = 1
b = 1
print(a is b) #ture
print(a == b) # ture
c = [1, 2]
d = [1, 2]
print(c is d) #F
print(c == d)#T
print(c is not d)#T
print(1 in d)#T
print(1 not in d) #F
```

