# 时间

```python
import time
ticks = time.time()

print("当前时间戳为：",ticks)
```

## 获取当前时间

```python
import time
 
localtime = time.localtime(time.time())
print("本地时间为 :", localtime)
```

## 获取格式化时间

```python
import time
 
localtime = time.asctime( time.localtime(time.time()) )
print "本地时间为 :", localtime
```

## 格式化日期

我们可以使用 time 模块的 strftime 方法来格式化日期，：

```python
time.strftime(format[, t])

# 格式化成2016-03-20 11:45:39形式
print time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()) 
```

{% embed url="https://www.runoob.com/python/python-date-time.html" %}
