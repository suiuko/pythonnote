# 多态

## 前沿回顾

**面向对象三大特性**

1. **封装** 根据 **职责** 将 **属性** 和 **方法** **封装** 到一个抽象的 **类** 中
   * 定义类的准则
2. **继承** **实现代码的重用**，相同的代码不需要重复的编写
   * 设计类的技巧
   * 子类针对自己特有的需求，编写特定的代码
3. **多态** 不同的 **子类对象** 调用相同的 **父类方法**，产生不同的执行结果
   * **多态** 可以 **增加代码的灵活度**
   * 以 **继承** 和 **重写父类方法** 为前提
   * 是调用方法的技巧，**不会影响到类的内部设计**

## 1 多态案例演练

#### 需求

1. 在`dog` 类中封装方法 `game`&#x20;
2. 定义 `xtd` 继承`dog` 并且重写 game 方法
3. 定义`Person` 类，并且封装一个 **和狗玩** 的方法

```python
class Dog(object):
    def __init__(self,name) -> None:
        
        self.name = name
    
    def game(self):
        print("%s playing" %self.name)
        
class XiaoTianDog(Dog):
    def game(self):
        print("%s playing on the sky" %self.name)
        
class Person(object):
    def __init__(self,name) -> None:
        self.name = name
    
    def game_with_dog(self,dog):
        print("%s and %s are playing very happy"%(self.name, dog.name))
        
        # 让狗玩耍
        dog.game()
        
# 1. 创建一个狗对象
# wangcai = Dog("旺财")
wangcai = XiaoTianDog("飞天旺财")

# 2. 创建一个小明对象
xiaoming = Person("小明")

# 3. 让小明调用和狗玩的方法
xiaoming.game_with_dog(wangcai)
    
    
# 输出
# 小明 and 飞天旺财 are playing very happy
# 飞天旺财 playing on the sky
```
