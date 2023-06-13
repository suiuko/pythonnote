# 继承

## 1. 单继承

### 1.1 继承的概念、语法和特点

**继承的概念**：**子类** 拥有 **父类** 的所有 **方法** 和 **属性**

<figure><img src="../../../../.gitbook/assets/011_继承对比图示.png" alt=""><figcaption></figcaption></figure>

#### 1.1.1 继承的语法

```python
class 类名(父类名):
    pass
```

* **子类** 继承自 **父类**，可以直接 **享受** 父类中已经封装好的方法，不需要再次开发
* **子类** 中应该根据 **职责**，封装 **子类特有的** **属性和方法**

#### 1.1.2 继承、派生说法

```python
class Animal:

    def eat(self):
        print("吃---")

    def drink(self):
        print("喝---")

    def run(self):
        print("跑---")

    def sleep(self):
        print("睡---")


class Dog(Animal):

    # 子类拥有父类的所有属性和方法
    # def eat(self):
    #     print("吃")
    #
    # def drink(self):
    #     print("喝")
    #
    # def run(self):
    #     print("跑")
    #
    # def sleep(self):
    #     print("睡")

    def bark(self):
        print("汪汪叫")

# 创建一个对象 - 狗对象
wangcai = Dog()

wangcai.eat()
wangcai.drink()
wangcai.run()
wangcai.sleep()
wangcai.bark()
```

* `Dog` 类是 `Animal` 类的**子类**，`Animal` 类是 `Dog` 类的**父类**，`Dog` 类从 `Animal` 类**继承**
* `Dog` 类是 `Animal` 类的**派生类**，`Animal` 类是 `Dog` 类的**基类**，`Dog` 类从 `Animal` 类**派生**

#### 1.1.3 继承的传递性

* `C` 类从 `B` 类继承，`B` 类又从 `A` 类继承
* 那么 `C` 类就具有 `B` 类和 `A` 类的所有属性和方法
* **子类** 拥有 **父类** 以及 **父类的父类** 中封装的所有 **属性** 和 **方法**

### **1.2 方法的重写**

> **子类** 拥有 **父类** 的所有 **方法** 和 **属性**\
> **子类** 继承自 **父类**，可以直接 **享受** 父类中已经封装好的方法，不需要再次开发

**重写** 父类的方法有两种情况：\
1\. 覆盖父类的方法\
2\. 对父类的方法进行扩展

#### 1.2.1 覆盖父类的方法

如果在开发中，父类的方法实现 和 子类的方法实现，完全不同，就可以使用 覆盖 的方法，在子类中 重新编写 父类的方法实现

> 具体的实现方式，就相当于在  子类中 定义了一个 和父类同名的方法并且实现
>
> 重写后，在运行时，只会调用子类中重写的方法，而不再会调用 父类封装的方法

```python
class Animal:
    def eat(self):
        print("吃")
        
    def drnk(self):
        print("喝")
        
    def run(self):
        print("跑")
        
    def sleep(self):
        print("睡觉")
        
class Dog(Animal):
    
    def bark(self):
        print("汪汪叫")

class XTQ(Dog):
    
    def fly(self):
        print("我会飞")

    def bark(self):
        print("叫得跟神一样")
        
        

# 创建一个啸天犬的对象
xtq = XTQ()
# xtq.fly()

# 如果子类中，重写了父类的方法
# 在使用子类对象调用方法，会调用子类中重写的方法

xtq.bark()
# xtq.eat()
```

#### 1.2.2 对父类方法进行 扩展

如果在开发中，子类的方法实现中包含父类的方法实现，父类原本封装的方法实现是子类方法的一部分

* 就可以使用 **扩展** 的方式
  1. **在子类中** **重写** 父类的方法
  2. 在需要的位置使用 `super().父类方法` 来调用父类方法的执行
  3. 代码其他的位置针对子类的需求，编写 **子类特有的代码实现**

#### **1.2.3 super**

* `super()` 就是使用 `super` 类创建出来的对象
* 在 **重写父类方法时**，调用 **在父类中封装的方法实现**

```python
def bark(self):
        # 1. 针对子类特有的需求
        print("神一样")
        
        # 2. 使用 super 调用父类封装的方法
        super().bark()
        # 3. 添加其他 代码
        print("*&^")
        
# 输出
# 神一样
# 汪汪叫
# *&^
```

注意： 如果使用子类调用方法， 会出现递归调用 --- 会出现死循环

### 1.3 父类的 私有属性和私有方法

1. **子类对象** **不能** 在自己的方法内部，**直接** 访问 父类的 **私有属性** 或 **私有方法**
2. **子类对象** 可以通过 **父类** 的 **公有方法** **间接** 访问到 **私有属性** 或 **私有方法**

> * **私有属性、方法** 是对象的隐私，不对外公开，**外界** 以及 **子类** 都不能直接访问
> * **私有属性、方法** 通常用于做一些内部的事情

<figure><img src="../../../../.gitbook/assets/013_父类的私有属性和私有方法.png" alt="" width="220"><figcaption></figcaption></figure>

* `B` 的对象不能直接访问 `__num2` 属性
* `B` 的对象不能在 `demo` 方法内访问 `__num2` 属性
* `B` 的对象可以在 `demo` 方法内，调用父类的 `test` 方法
* 父类的 `test` 方法内部，能够访问 `__num2` 属性和 `__test` 方法

```python
class A:

    def __init__(self):

        self.num1 = 100
        self.__num2 = 200

    def __test(self):
        print("私有方法 %d %d" % (self.num1, self.__num2))


class B(A):

    def demo(self):

        # 1. 在子类的对象方法中，不能访问父类的私有属性
        # print("访问父类的私有属性 %d" % self.__num2)

        # 2. 在子类的对象方法中，不能调用父类的私有方法
        # self.__test()
        pass

# 创建一个子类对象
b = B()
print(b)

b.demo()

# 在外界不能直接访问对象的私有属性/调用私有方法
# print(b.__num2)
# b.__test()
```

#### 1.3.1 如何调用私有方法和属性？

{% content-ref url="../si-you-shu-xing-he-si-you-fang-fa/ru-he-tiao-yong-si-you-fang-fa.md" %}
[ru-he-tiao-yong-si-you-fang-fa.md](../si-you-shu-xing-he-si-you-fang-fa/ru-he-tiao-yong-si-you-fang-fa.md)
{% endcontent-ref %}

## 2 多继承

**子类** 可以拥有 **多个父类**，并且具有 **所有父类** 的 **属性** 和 **方法**

```python
class 子类名(父类名 1,父类名 2 ...)
    pass
```

### 2.1 多继承的使用注意事项

**开发时，应该尽量避免这种容易产生混淆的情况！** —— 如果 **父类之间** 存在 **同名的属性或者方法**，应该 **尽量避免** 使用多继承

### 2.1.2 python 中的 MRO ---- 方法搜索顺序

Python 中针对 类 提供了一个内置属性 `__mro__` 可以查看方法搜索的顺序

### 2.2 新式类与旧式(经典)类

* **新式类**：以 `object` 为基类的类，**推荐使用**
* **经典类**：不以 `object` 为基类的类，**不推荐使用**

**新式类** 和 **经典类** 在多继承时 —— **会影响到方法的搜索顺序**

<pre class="language-python"><code class="lang-python"><strong># 新式类：
</strong><strong>class 类名(object):
</strong>    pass
</code></pre>
