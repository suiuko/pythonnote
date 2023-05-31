# 函数基础

## 函数快速体验

### 1.1 体验

定义函数 -- 封装独立的功能

调用函数 -- 享受封装的成果

函数的作用，在开发程序时，使用函数可以提高编写的效率以及代码的重用

#### 大致步骤

* 新建项目
* 复制之前完成的 XX 文件
* 修改文件，增加函数定义 function():
* 新建另外一个文件，使用 import 导入 并且调用函数

### 2.1 函数的定义

定义函数的格式：

```python
def 函数名():
    函数封装的代码
```

函数名称 的命名应该 符合 标识符的命名规则

* 可以由 字母、下划线、数字组成
* 不能以数字开头
* 不能与关键字重名

### 2.2 函数调用

通过 函数名() 来进行调用

练习：通过函数来调用hello

```python
#
def say_hello():
    print("hello1")
    print("hello2")
    print("hello3")

say_hello()
```

### 2.3 函数演练

编写一个打招呼的函数，封装三行打招呼的代码

<pre class="language-python"><code class="lang-python"># 
name = "小明"
<strong># 定义一个
</strong>def say_hello():
    print("hello1")
    print("hello2")
    print("hello3")

print(name)

say_hello()

print(name)
</code></pre>

在 使用函数名 调用函数之前，必须保证函数已经被定义存在，在才可以调用

### 2.4 pycharm 调试工具

F8 step over 可以单步执行代码，会把函数调用看作是一行代码直接执行

F7 step into 可以单步执行代码，如果是函数 会进入函数内部

### 2.5 函数文档注释

在开发中，应该在 定义函数的下方，使用 连续的三对引号

在 连续的三对引号 之间编写对函数的说明文字

在 函数调用 位置，使用 ctrl+q 可以查看函数的说明信息

```python
# 展示正规写法
# 开始 在函数上方有两个空行

def say_hello():
    """ 打招呼 """ # 对函数进行解释
    
    print("hello") # 函数的内容
    
say_hello() # 调用函数
```

## 3 函数的参数

练习：1. 开发一个sum\_2\_num 的函数； 2. 函数能够实现连个数字的求和功能

```python
def sum_2_num():
    num1 = 10
    num2 = 20
    result = num1 + num2
    
    print("%d + %d = %d" %(num1, num2, result))

sum_2_num()

# 问题是 只能固定数值相加
```

### 3.1 函数参数的使用

在函数名的后面的 小括号内部填写参数

```python
def sum_2_num(num1,num2): # 这两个参数是形参
    return = num1 + num2 
    
    print("%d + %d = %d" %(num1,num2,result))

sum_2_num(50,20) # 这两个是实参
```

### 3.2 参数的作用

函数，把 具有独立功能的代码块 组织为一个小模块，在需要的时候调用

参数，增加函数的通用性，有数据处理的能力

### 3.3 形参和实参

形参：定义函数时，接受参数，作为变量使用

实参：调用函数时，把数据传输到函数内部使用

## 4 函数的返回值

返回值 是函数 完成工作后，最后 给调用者的 一个结果

在函数中使用 return 关键字可以返回结果

> 注意：return 表示返回，后续的代码将不会执行

```python
def sum_2_num(num1,num2):
    """对两个数字求和"""
    result = num1 + num2

    return result
# 可以使用变量来接受函数执行的结果
sum_result = sum_2_num(10,20)
print("计算结果：%d" % sum_result)

```

## 5 函数的嵌套调用

一个函数里面调用了另一个函数

```python
# 在test2中调用了另一个函数test1
def test1():
    print("*" * 50)
    print("test 1")
    print("*" * 50)

def test2():
    print("-" * 50)
    print("test 2")

    test1()

    print("-" * 50)

test2()
```

### 函数嵌套训练 —— 打印分割线

需求一：定义一个 `print_line` 函数能够打印 `*` 组成的一条分割线

```python
def print_line(char):
    print("*" * 50)
```

需求二：定义一个函数能过打印 由任意字符组成的 分割线

```python
def print_line(char):
    print(char * 50)
```

需求三：定义一个函数能够打印任意重复次数的分割线

```python
def print_lint(char,times):
    print(char * times)
```

```python
# 打印多行

def print_line(char,times):
    print(char * times)
    
def print_lines(cahr,times,row1):
    """
    
    :param char: 分割线使用的分隔字符
    :param times: 分割线重复的次数
    """
    row = 0
    while row < row1:
        print_line(char,times)
        row +=1

print_lines("-",20,5)
```

## 6 使用模块中的函数

模块是工具包，就需要导入 `import` 这个模块

每一个以扩展名 `py` 结尾的源代码文件就是一个模块

### 6.1 第一个模块

```python
# 新建一个分割线模块.py
# 完成打印多条分割线，同时增加一个字符串变量

#这里是 分割线模块.py
def print_line(char,times):
    print(char * times)
    
def print_lines(char,times,row1):
    """
    
    :param char: 分割线使用的分隔字符
    :param times: 分割线重复的次数
    """
    row = 0
    while row < row1:
        print_line(char,times)
        row +=1

# 这里是 调用.py
import 分割线模块.py
分割线模块.print_lines("-",50,5)

```

可以使用 `模块名.变量` / `模块名.函数` 的方式，使用这个模块中定义的变量或者函数

### 6.2 模块名也是标识符

标识符可以由 字母、 下划线 和 数字 组成

不能以数字开头

不能与关键字重名

### 6.3 pyc 文件

pyc文件是变异过的文件，会存放在缓存文件夹中

