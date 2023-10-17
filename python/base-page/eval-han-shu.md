# eval 函数

`eval()` 函数十分强大 —— **将字符串** 当成 **有效的表达式** 来求值 并 **返回计算结**

```python
# 基本的数学计算
In [1]: eval("1 + 1")
Out[1]: 2

# 字符串重复
In [2]: eval("'*' * 10")
Out[2]: '**********'

# 将字符串转换成列表
In [3]: type(eval("[1, 2, 3, 4, 5]"))
Out[3]: list

# 将字符串转换成字典
In [4]: type(eval("{'name': 'xiaoming', 'age': 18}"))
Out[4]: dict
```

### 不要滥用 `eval`

> 在开发时千万不要使用 `eval` 直接转换 `input` 的结果
>
> 如果用户用 import 调用 os 方法可以执行任何的终端命令

```python
__import__('os').system('ls')
```

* 等价代码

```python
import os
​
os.system("终端命令")
```

* 执行成功，返回 0
* 执行失败，返回错误信息
