# 如何调用私有方法

在父类创建一个公共方法来调用私有方法

<pre class="language-python"><code class="lang-python">class Women:

    def __init__(self, name):

        self.name = name
        # 不要问女生的年龄
        self.__age = 18

    def __secret(self):
        print("我的年龄是 %d" % self.__age)
        
    def show_secret(self):
        print(self.__age)
        self.__secret()
        

xiaofang = Women("小芳")
# 私有属性，外部不能直接访问
#print(xiaofang.__age)
xiaofang.show_secret()

# 私有方法，外部不能直接调用
# xiaofang.__secret()

# 输出
# 18
<strong># 我的年龄是 18
</strong></code></pre>
