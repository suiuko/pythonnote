# 面向对象封装案例

## 1 封装

1. **封装** 是面向对象编程的一大特点
2. 面向对象编程的 **第一步** —— 将 **属性** 和 **方法** **封装** 到一个抽象的 **类** 中
3. **外界** 使用 **类** 创建 **对象**，然后 **让对象调用方法**
4. **对象方法的细节** 都被 **封装** 在 **类的内部**

## 2 案例学习 ---- 小明爱跑步

### 需求

1. **小明** **体重** `75.0` 公斤
2. 小明每次 **跑步** 会减肥 `0.5` 公斤
3. 小明每次 **吃东西** 体重增加 `1` 公斤

| person                                                                           |
| -------------------------------------------------------------------------------- |
| <p>name<br>weight</p>                                                            |
| <p>__init__(self,name,weight):<br>__str__(self):<br>run(self):<br>eat(self):</p> |

提示：在 **对象的方法内部**，是可以 **直接访问对象的属性** 的！

```python
class Person:
    """人类"""

    def __init__(self, name, weight):
				# self.属性 = 形参
        self.name = name
        self.weight = weight

    def __str__(self):

        return "我的名字叫 %s 体重 %.2f 公斤" % (self.name, self.weight)

    def run(self):
        """跑步"""

        print("%s 爱跑步，跑步锻炼身体" % self.name)
        self.weight -= 0.5

    def eat(self):
        """吃东西"""

        print("%s 是吃货，吃完这顿再减肥" % self.name)
        self.weight += 1


xiaoming = Person("小明", 75)

xiaoming.run()
xiaoming.eat()
xiaoming.eat()

print(xiaoming)
```

### 2.1 小明爱跑步扩展 -- 添加小美

