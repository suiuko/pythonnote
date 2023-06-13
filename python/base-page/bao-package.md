# 包 package

## 1 概念

* **包** 是一个 **包含多个模块** 的 **特殊目录**
* 目录下有一个 **特殊的文件** `__init__.py`
* 包名的 **命名方式** 和变量名一致，**小写字母** + `_`

使用 `import 包名` 可以一次性导入 **包** 中 **所有的模块**

### **1.1 案例**

1. 新建一个 `hm_message` 的 **包，**包下面默认创建`__init__.py` 这个文件
2. 在目录下，新建两个文件 `send_message` 和 `receive_message`
3. 在 `send_message` 文件中定义一个 `send` 函数
4. 在 `receive_message` 文件中定义一个 `receive` 函数
5. 在外部直接导入 `hm_message` 的包

#### 1.1.1 \_\_init.py

* 要在外界使用 **包** 中的模块，需要在 `__init__.py` 中指定 **对外界提供的模块列表**

```python
# 从 当前目录 导入 模块列表
from . import send_message
from . import receive_message
```

#### 1.1.2 receive\_message.py

```python
def receive():
    return "收到了返回"
```

#### 1.1.3 send\_message.py

```python
def send(text):
    print("正在发送 %s" %text)
```

#### 1.1.4 导入包.py

<pre class="language-python"><code class="lang-python">import hm_message

hm_message.send_message.send("hello")
txt = hm_message.receive_message.receive()
print(txt)

#输出
#正在发送 hello
<strong>#收到了返回
</strong></code></pre>
