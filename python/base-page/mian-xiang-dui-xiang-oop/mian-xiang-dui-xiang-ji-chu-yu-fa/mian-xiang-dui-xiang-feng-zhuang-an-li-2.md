# 面向对象封装案例2

## 1 士兵突击

**需求**

1. **士兵** **许三多** 有一把 **AK47**
2. **士兵** 可以 **开火**
3. **枪** 能够 **发射** 子弹
4. **枪** 装填 **装填子弹** —— **增加子弹数量**

| soldier                             | gun                                                                    |
| ----------------------------------- | ---------------------------------------------------------------------- |
| <p>name<br>gun</p>                  | <p>model<br>bullet_count</p>                                           |
| <p>__init__(self)<br>fire(self)</p> | <p>__init__(self,model):<br>add_bullet(self,count):<br>shoot(self)</p> |

### 1.1 开发枪类

#### shoot 方法需求：

1\. 判断是否有子弹\
2\. 使用 print 提示射击，并且输出子弹数量

```python
class Gun:
    def __init__(self,model):
        
        # 1. 枪的型号
        self.model = model
        
        # 2. 子弹数量
        self.bullet_count = 0
        pass
    
    def add_bullet(self,count):
        self.bullet_count += count
        
    def shoot(self):
        
        # 1. 判断子弹数量
        if self.bullet_count <=0:
            print("[%s] 没有子弹" % self.model)
            
            return
        
        # 2. 发射子弹，-1
        self.bullet_count -=1
        
        # 3. 提示发射信息
        print("[%s] tututu [%d]" %(self.model,self.bullet_count))
        

# 1. 创建枪的对象
ak47 = Gun("ak47")
ak47.add_bullet(50)
ak47.shoot()
```

### 1.2 开发士兵类

> 假设：每个新兵都没有枪

#### 1.2.1 定义没有初始值的属性

在定义属性时，如果 不知道设置什么初始值，可以设置为 `none` ，这表示一个 空对象，没有方法和属性，是一个特殊的常量

#### fire 方法需求

1.判断是否有枪，2.喊口号 3.装填子弹 4.射击

```python
class Soldier:

    def __init__(self, name):

        # 姓名
        self.name = name
        # 枪，士兵初始没有枪 None 关键字表示什么都没有
        self.gun = None

    def fire(self):

        # 1. 判断士兵是否有枪
        if self.gun is None:
            print("[%s] 还没有枪..." % self.name)

            return

        # 2. 高喊口号
        print("冲啊...[%s]" % self.name)

        # 3. 让枪装填子弹
        self.gun.add_bullet(50)

        # 4. 让枪发射子弹
        self.gun.shoot()
```

**小结**

1. 创建了一个 **士兵类**，使用到 `__init__` 内置方法
2. 在定义属性时，如果 **不知道设置什么初始值**，可以设置为 `None`
3. 在 **封装的** 方法内部，还可以让 **自己的** **使用其他类创建的对象属性** 调用已经 **封装好的方法**

```python
class Gun:
    def __init__(self,model):
        
        # 1. 枪的型号
        self.model = model
        
        # 2. 子弹数量
        self.bullet_count = 0
        pass
    
    def add_bullet(self,count):
        self.bullet_count += count
        
    def shoot(self):
        
        # 1. 判断子弹数量
        if self.bullet_count <=0:
            print("[%s] 没有子弹" % self.model)
            
            return
        
        # 2. 发射子弹，-1
        self.bullet_count -=1
        
        # 3. 提示发射信息
        print("[%s] tututu [%d]" %(self.model,self.bullet_count))
        

class Soldier:
    def __init__(self,name):
        # 1. 姓名
        self.name = name
        
        # 2. 枪
        self.gun = None
        
    def fire(self):
        # 1. 士兵是否有枪
        
        if self.gun == None:
            print("[%s]还没有枪" %self.name)
            
            return
        
        # 2. 喊口号
        
        print("[%s]有枪，reloading" %self.name)
        
        # 3. 让枪装填子弹
        
        self.gun.add_bullet(50)
        
        # 4. 让枪发射子弹
        self.gun.shoot()
    
# 1. 创建枪的对象
ak47 = Gun("ak47")
# ak47.add_bullet(50)
# ak47.shoot()

# 2. 创建许三多
xsd = Soldier("许三多")
xsd.gun = ak47
xsd.fire()
print(xsd.gun)
```
