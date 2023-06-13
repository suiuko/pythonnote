# 方法综合案例

## 1 需求

1. 设计一个 `Game` 类
2. 属性：
   * 定义一个 **类属性** `top_score` 记录游戏的 **历史最高分**
   * 定义一个 **实例属性** `player_name` 记录 **当前游戏的玩家姓名**
3. 方法：
   * **静态方法** `show_help` 显示游戏帮助信息
   * **类方法** `show_top_score` 显示历史最高分
   * **实例方法** `start_game` 开始当前玩家的游戏
4. 主程序步骤
   * 查看帮助信息
   * 查看历史最高分
   * 创建游戏对象，开始游戏

<figure><img src="../../../../.gitbook/assets/021_方法综合案例.png" alt=""><figcaption></figcaption></figure>

### **案例小结**

1. <mark style="color:orange;">**实例方法**</mark> <mark style="color:orange;"></mark><mark style="color:orange;">—— 方法内部需要访问</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**实例属性**</mark>
   * <mark style="color:orange;">**实例方法**</mark> <mark style="color:orange;"></mark><mark style="color:orange;">内部可以使用</mark> <mark style="color:blue;">**类名.**</mark>  <mark style="color:orange;">访问类属性</mark>
2. <mark style="color:orange;">**类方法**</mark> <mark style="color:orange;"></mark><mark style="color:orange;">—— 方法内部</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**只**</mark> <mark style="color:orange;"></mark><mark style="color:orange;">需要访问</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**类属性**</mark>
3. <mark style="color:orange;">**静态方法**</mark> <mark style="color:orange;"></mark><mark style="color:orange;">—— 方法内部，不需要访问</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**实例属性**</mark> <mark style="color:orange;"></mark><mark style="color:orange;">和</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**类属性**</mark>

**提问**

如果方法内部 即需要访问 **实例属性**，又需要访问 **类属性**，应该定义成什么方法？

**答案**

* 应该定义 **实例方法**
* 因为，**类只有一个**，在 **实例方法** 内部可以使用 **类名.** 访问类属性

```python
class Game(object):
    
    # 历史最高分
    
    top_score = 0
    
    def __init__(self,player_name):
        self.player_name = player_name
        
    @staticmethod
    def show_help():
        print("帮助信息")
        
    @classmethod
    def show_top_score(cls):
        print("历史记录 %d" %cls.top_score)
    
    def start_game(self):
        print("%s 开始游戏" %self.player_name)
        
# 1. 查看游戏的帮助信息

Game.show_help()

# 2. 查看历史最高分

Game.show_top_score()

# 3. 创建游戏对象

game1 = Game("小明")

game1.start_game()


# 输出
#帮助信息
#历史记录 0
#小明 开始游戏
```
