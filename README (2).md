---
description: This is a python note which 'heima' project on bilibili
---

# 循环语句

## 1.1 循环

```python
初始条件设置 —— 通常是重复执行的计数器
while 条件(判断 计数器 是否达到 目标次数):
    条件满足时，做的事情1
    条件满足时，做的事情1

    处理条件(计数器 +1) // i = i+1
```

```python
# 打印五遍
i =1
while i<=5:
    print("hello")
    i = i+1
```

#### 死循环

忘记在循环内部修改循环的判断条件

## 1.2 赋值运算符

<table><thead><tr><th>描述</th><th width="200"></th></tr></thead><tbody><tr><td>+=</td><td>c+=a--> c = c+a</td></tr><tr><td>-=</td><td></td></tr><tr><td>*=</td><td></td></tr><tr><td>/=</td><td>除法</td></tr><tr><td>//=</td><td>整除</td></tr><tr><td>%=</td><td>取模（余数）</td></tr><tr><td>**=</td><td>幂赋值</td></tr></tbody></table>

## 1.3 计数方法

程序计数法是从0开始

## 1.4 循环计算

练习：计算0-100之间的数字求和

<pre class="language-python"><code class="lang-python"><strong>
</strong># 计算0-100之间的数字求和
# 定义一个整数循环次数
i=0
# 定义结果
result = 0
#开始
while i&#x3C;=100:
    # print(i)
    result +=i
    i+=1
print(result)

    
</code></pre>

练习：计算0-100之前的偶数的累积求和结果

```python

# 0-100之间所有的偶数之和

i =0
result = 0
while i<=100:
    if i % 2 ==0: #奇数为 i % 2 != 0
        result +=i
    i += 1    
print(result)
```

## 1.4.1 break 和 continue

break 某一条件满足时，推出循环，不再执行后续重复的代码

continue 某一条件满足时，不执行后续重复代码，继续下一个循环

break 和 continue 只针对 **当前所在循环** 有效

```python

# 在continue中 可能会出现死循环，例如：

i = 0
while i < 10:
    if i ==3:
        continue 
    print(i)
    i += 1 #这样写会导致死循环
    

# 正确情况
i = 0
while i < 10:
    if i == 3:
        i += 1 # 再此添加一次循环，跳出死循环
        continue
    print(i)
    i += 1

```

## 1.4.2 循环嵌套

### while 循环嵌套

```python
while 条件 1:
    条件满足时，做的事情1
    条件满足时，做的事情2
    while 条件 2:
        条件满足时，做的事情1
        条件满足时，做的事情2
        
        处理条件2
    
    处理条件1
```

```python
# 打印小星星 在控制台输出五行 *

row = 1 # 定义一个计数器变量
# 开始循环
while row <= 5:
    print("*" * row)
    row += 1


# 进阶操作，如果没有提供拼接字符串的操作该怎么办
# 1: 完成5行内容的简单输出
# 2：分析每行内部的 * 应该怎么处理

row = 1
while row <= 5:
    # 每一行要打印的星星就是和当前的行数是一致的
    # 增加一个小的循环，专门负责之前行中，每一 列 的星星显示
    
    # 1. 定义一个列计数器变量
    col = 1
    # 2. 开始循环
    while col <= row:
        # print("%d" % col)
        print("*" , end="")
        col += 1
        
    # print("每 %d 行" % row)
    print("") # 上方指定了end， 所以要重新换行
    row += 1

```

默认情况下，_print_ 函数输出内容后，会自动在内容末尾增加换行

如果不希望末尾增加换行，可以在 _print_ 函数输出内容的后面增加 **,end=""**

```python
# 输出格式如下
# 不会换行
print("*" , end="") # end里面输入什么 就会显示什么

#会换行
print("")
```

练习： 九九乘法表

```python
# 九九乘法表

row = 1
while row <= 9:
    
    col = 1
    while col <= row:
        # print("*", end="")
        # print("1 * %d = 1 " % row , end=" ") # 来看出 乘号后面是行号
        print("%d * %d = %d " % (col , row, col * row) , end=" ")
        col += 1
    # print("%d" %row)
    print("")
    row += 1
    
    
# 但是在输出的时候 会发现，下方列并不对齐 所以需要修正一下

# \t 在控制台输出一个制表符，协助在输出文本时 垂直方向 保持对齐
# \n 在控制台输出一个 换行符
    
```

```
\t 在控制台输出一个制表符，协助在输出文本时 垂直方向 保持对齐
\n 在控制台输出一个 换行符
```

| 转义字符 | 描述    |
| ---- | ----- |
| \\\\ | 反斜杠符号 |
| \\\` | 单引号   |
| \\"  | 双引号   |
| \n   | 换行    |
| \t   | 横向制表符 |
| \r   | 回车    |

### for 循环

```python
for 成员元素 in 集合对象:
    子代码1
else: 
    子代码2

# 集合对象 可以是数字序列、字符串、列表、元组、字典等

```
