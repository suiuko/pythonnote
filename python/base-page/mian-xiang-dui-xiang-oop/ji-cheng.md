# 继承

## 1. 单继承

### 1.1 继承的概念、语法和特点

**继承的概念**：**子类** 拥有 **父类** 的所有 **方法** 和 **属性**

<figure><img src="../../../.gitbook/assets/011_继承对比图示.png" alt=""><figcaption></figcaption></figure>

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

重写 父类的方法有两种情况：\
1\. 覆盖父类的方法\
2\. 对父类的方法进行扩展

#### 1.2.1 覆盖父类的方法

