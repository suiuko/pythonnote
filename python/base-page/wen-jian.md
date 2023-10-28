# 文件

{% embed url="https://www.runoob.com/python/file-methods.html" %}

## 1 文件的概念

### 1.1 文件的概念和作用

计算机的 **文件**，就是存储在某种 **长期储存设备** 上的一段 **数据**

### 1.2 文件的储存方式

#### **1.2.1 文本文件和二进制文件**

* 文本文件
  * 可以使用 **文本编辑软件** 查看
  * 本质上还是二进制文件
  * 例如：python 的源程序
* 二进制文件
  * 保存的内容 不是给人直接阅读的，而是 **提供给其他软件使用的**
  * 例如：图片文件、音频文件、视频文件等等
  * 二进制文件不能使用 **文本编辑软件** 查看

## 2 文件的基本操作

### 2.1 操作文件的套路

1. 打开文件
2. 读、写文件
   * **读** 将文件内容读入内存
   * **写** 将内存内容写入文件
3. 关闭文件

### 2.2 操作文件的函数/方法

<table data-header-hidden><thead><tr><th width="263"></th><th></th></tr></thead><tbody><tr><td>open</td><td>打开文件，并且返回文件操作对象</td></tr><tr><td>read</td><td>将文件内容读取到内存</td></tr><tr><td>write</td><td>将指定内容写入文件</td></tr><tr><td>close</td><td>关闭文件</td></tr></tbody></table>

* `open` 函数负责打开文件，并且返回文件对象
* `read`/`write`/`close` 三个方法都需要通过 **文件对象** 来调用

### 2.3 read 方法 —— 读取文件

* `open` 函数的第一个参数是要打开的文件名（文件名区分大小写）
  * 如果文件 **存在**，返回 **文件操作对象**
  * 如果文件 **不存在**，会 **抛出异常**
* `read` 方法可以一次性 **读入** 并 **返回** 文件的 **所有内容**
* `close` 方法负责 **关闭文件**
  * 如果 **忘记关闭文件**，**会造成系统资源消耗，而且会影响到后续对文件的访问**
* **注意**：`read` 方法执行后，会把 **文件指针** 移动到 **文件的末尾**

```python
# 1. 打开
file  = open("README.md")

# 2. 读取
text = file.read()
print(text)

# 3. 关闭
file.close()
```

#### **2.3.1 文件指针（知道）**

* **文件指针** 标记 **从哪个位置开始读取数据**
* **第一次打开** 文件时，通常 **文件指针会指向文件的开始位置**
* 当执行了 `read` 方法后，**文件指针** 会移动到 **读取内容的末尾**
  * 默认情况下会移动到 **文件末尾**

### **2.4 打开文件的方式**

`open` 函数默认以 **只读方式** 打开文件，并且返回文件对象

```python
f = open("文件名","访问方式")
```

<table data-header-hidden><thead><tr><th width="209">访问方式</th><th>说明</th></tr></thead><tbody><tr><td>r</td><td>以<strong>只读</strong>方式打开文件。文件的指针将会放在文件的开头，这是<strong>默认模式</strong>。如果文件不存在，抛出异常</td></tr><tr><td>w</td><td>以<strong>只写</strong>方式打开文件。如果文件存在会被覆盖。如果文件不存在，创建新文件</td></tr><tr><td>a</td><td>以<strong>追加</strong>方式打开文件。如果该文件已存在，文件指针将会放在文件的结尾。如果文件不存在，创建新文件进行写入</td></tr><tr><td>r+</td><td>以<strong>读写</strong>方式打开文件。文件的指针将会放在文件的开头。如果文件不存在，抛出异常</td></tr><tr><td>w+</td><td>以<strong>读写</strong>方式打开文件。如果文件存在会被覆盖。如果文件不存在，创建新文件</td></tr><tr><td>a+</td><td>以<strong>读写</strong>方式打开文件。如果该文件已存在，文件指针将会放在文件的结尾。如果文件不存在，创建新文件进行写入</td></tr></tbody></table>

### 2.5 按行读取文件内容

`read` 方法默认会把文件的 **所有内容** **一次性读取到内存**

#### **2.5.1 readline 方法**

**readline 方法**可以一次读取一行内容，方法执行后，会把文件指针移动到下一行，准备再次读取

#### 2.5.2 读取大文件的正确方法

```python
# 打开文件
file = open("README")

while True:
    # 读取一行内容
    text = file.readline()

    # 判断是否读到内容
    if not text:
        break

    # 每读取一行的末尾已经有了一个 `\n`
    print(text, end="")

# 关闭文件
file.close()
```

### 2.6 文件读写案例 —— 复制文件

#### 2.6.1 小文件复制

```python
# 1. 打开文件
file_read = open("README")
file_write = open("README[复件]", "w")

# 2. 读取并写入文件
text = file_read.read()
file_write.write(text)

# 3. 关闭文件
file_read.close()
file_write.close()
```

#### 2.6.2 大文件复制

```python
# 1. 打开文件
file_read = open("README")
file_write = open("README[复件]", "w")

# 2. 读取并写入文件
while True:
    # 每次读取一行
    text = file_read.readline()

    # 判断是否读取到内容
    if not text:
        break

    file_write.write(text)

# 3. 关闭文件
file_read.close()
file_write.close()
```

## 3 文件/目录的常用管理操作

* 在 **终端** / **文件浏览器**、 中可以执行常规的 **文件** / **目录** 管理操作，例如：
  * 创建、重命名、删除、改变路径、查看目录内容、……
* 在 `Python` 中，如果希望通过程序实现上述功能，需要导入 `os` 模块

### 2.1 文件操作

<table data-header-hidden><thead><tr><th width="141"></th><th width="127"></th><th></th></tr></thead><tbody><tr><td>rename</td><td>重命名文件</td><td><code>os.rename(源文件名, 目标文件名)</code></td></tr><tr><td>remove</td><td>删除文件</td><td><code>os.remove(文件名)</code></td></tr></tbody></table>

### 2.2 目录操作

<table data-header-hidden><thead><tr><th width="139">方法名</th><th>说明</th><th>示例</th></tr></thead><tbody><tr><td>listdir</td><td>目录列表</td><td><code>os.listdir(目录名)</code></td></tr><tr><td>mkdir</td><td>创建目录</td><td><code>os.mkdir(目录名)</code></td></tr><tr><td>rmdir</td><td>删除目录</td><td><code>os.rmdir(目录名)</code></td></tr><tr><td>getcwd</td><td>获取当前目录</td><td><code>os.getcwd()</code></td></tr><tr><td>chdir</td><td>修改工作目录</td><td><code>os.chdir(目标目录)</code></td></tr><tr><td>path.isdir</td><td>判断是否是文件</td><td><code>os.path.isdir(文件路径)</code></td></tr></tbody></table>

> 提示：文件或者目录操作都支持 **相对路径** 和 **绝对路径**

### 4.1 ASCII 编码和 UNICODE 编码

**`ASCII` 编码**

* 计算机中只有 `256` 个 `ASCII` 字符
* 一个 `ASCII` 在内存中占用 **1 个字节** 的空间
  * `8` 个 `0/1` 的排列组合方式一共有 `256` 种，也就是 `2 ** 8`

<figure><img src="../../.gitbook/assets/001_ASCII编码表1.jpg" alt=""><figcaption></figcaption></figure>

### 4.2 Ptyhon 2.x 中如何使用中文

> Python 2.x 默认使用 `ASCII` 编码格式 Python 3.x 默认使用 `UTF-8` 编码格式

* 在 Python 2.x 文件的 **第一行** 增加以下代码，解释器会以 `utf-8` 编码来处理 python 文件

```python
# *-* coding:utf8 *-*

也可以：

# coding=utf8
```

#### **4.2.1 unicode 字符串**

* 在 `Python 2.x` 中，即使指定了文件使用 `UTF-8` 的编码格式，但是在遍历字符串时，仍然会 **以字节为单位遍历** 字符串
* 要能够 **正确的遍历字符串**，在定义字符串时，需要 **在字符串的引号前**，增加一个小写字母 `u`，告诉解释器这是一个 `unicode` 字符串（使用 `UTF-8` 编码格式的字符串）

```python
# *-* coding:utf8 *-*

# 在字符串前，增加一个 `u` 表示这个字符串是一个 utf8 字符串
hello_str = u"你好世界"

print(hello_str)

for c in hello_str:
    print(c)
```

