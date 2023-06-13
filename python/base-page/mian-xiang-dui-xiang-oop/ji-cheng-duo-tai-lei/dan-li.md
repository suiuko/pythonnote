# 单例

## 1 单例设计模式

* **目的** —— 让 **类** 创建的对象，在系统中 **只有** **唯一的一个实例**
* 每一次执行 `类名()` 返回的对象，**内存地址是相同的**

### **1.1 单例设计模式的应用场景**

音乐播放对象

回收站对象

打印机对象

## 2 \_\_new\_\_方法

* 使用 **类名()** 创建对象时，`Python` 的解释器 **首先** 会 调用 `__new__` 方法为对象 **分配空间**
* `__new__` 是一个 由 `object` 基类提供的 **内置的静态方法**，主要作用有两个：
  *
    1. 在内存中为对象 **分配空间**
  *
    2. **返回** 对象的引用
* `Python` 的解释器获得对象的 **引用** 后，将引用作为 **第一个参数**，传递给 `__init__` 方法
* <mark style="color:orange;">重写</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`__new__`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">方法</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**一定要**</mark> <mark style="color:orange;">`return super().__new__(cls)`</mark>
*   可以使用：

    <pre class="language-python"><code class="lang-python"><strong>instance = None # 记录被创建对象引用
    </strong><strong># 调用父类的方法，为第一个对象分配空间
    </strong><strong>cls.instance = super().__new__(cls) 
    </strong></code></pre>
* 否则 Python 的解释器 **得不到** 分配了空间的 **对象引用**，**就不会调用对象的初始化方法**
* 注意：`__new__` 是一个静态方法，在调用时需要 **主动传递** `cls` 参数

> 重写 `__new__` 方法的代码非常固定

<figure><img src="../../../../.gitbook/assets/022_对象分配空间和初始化.png" alt=""><figcaption><p>对象分配空间和初始化</p></figcaption></figure>

```python
class MusicPlayer(object):
    
    def __new__(cls,*args,**kwargs): # 一个* 多值元组，两个* 多值字典，
        
        # 1. 创建对象时 new 会被调用
        print("创建对象，分配空间")
        
        # 2. 为对象分配空间
        instance = super().__new__(cls)
        # 3. 返回对象的引用
        return instance
        
    def __init__(self):
        print("播放器初始化")
        
# 创建播放器对象
player = MusicPlayer()

print(player)    
```

## 3 python中的单例

<figure><img src="../../../../.gitbook/assets/023_单例流程.png" alt=""><figcaption><p>单例流程</p></figcaption></figure>

* **单例** —— 让 **类** 创建的对象，在系统中 **只有** **唯一的一个实例**
  1. 定义一个 **类属性**，初始值是 `None`，用于记录 **单例对象的引用**
  2. 重写 `__new__` 方法
  3. 如果 **类属性** `is None`，调用父类方法分配空间，并在类属性中记录结果
  4. 返回 **类属性** 中记录的 **对象引用**

```python
class MusicPlayer(object):
    
    #记录第一个被创建对象引用
    
    instance = None
    
    def __new__(cls,*args,**kwargs):
        # 1. 判断类属性是否是空对象
        if cls.instance is None:
            # 2. 调用父类的方法，为第一个对象分配空间
            cls.instance = super().__new__(cls)
            
        # 3. 返回类属性保存的对象应用
        return cls.instance

# 创建多个对象
player1 = MusicPlayer()
print(player1)
player2 = MusicPlayer()
print(player2) 
```
