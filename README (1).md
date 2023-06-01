---
description: This part will explain Linux
---

# linux

## 1:常见Linux命令的基本使用

ls：查看当前文件下的内容

pwd：查看当前所在文件夹

cd\[目录名]：切换文件夹

touch\[文件名]：如果文件不存在，创建文件

mkdir\[目录名]：创建目录

rm\[文件名]：删除指定的文件名

clear：清屏

1>自动补全：

![](https://firebasestorage.googleapis.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-LtjBx5IzF3v0mLLELzT%2Fuploads%2F13KOx5ItyyY8g0hpKYZd%2Ffile.png?alt=media)

2>增经使用过的命令

![](https://firebasestorage.googleapis.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-LtjBx5IzF3v0mLLELzT%2Fuploads%2Fp76r8GmTjGdcuSxhqT8J%2Ffile.png?alt=media)

### 2：ls 命令说明

ls 可以列出目录的内容（类似于DOS下的dir命令）

linux下文件和目录的特点

* Linux文件或者目录名称最长256个字符
* 以 . 开头的文件为隐藏文件，需要用 -a 才能显示
* . 代表当前目录
* &#x20;.. 代表上一级目录

| 代码 | 内容                     |
| -- | ---------------------- |
| -a | 显示指定目录下所有子目录与文件，包括隐藏文件 |
| -l | 以列表方式显示文件的相思信息         |
| -h | 配合-l 以人性化的方式显示文件大小     |

### 3: ls 通用符的使用

| 通配符    | 含义                |
| ------ | ----------------- |
| ·      | 代表任意个数个字符         |
| ？      | 代表任意一个字符，至少一个     |
| \[ ]   | 表示可以匹配字符组中的任意一个   |
| \[abc] | 匹配a、b、c中的任意一个     |
| \[a-f] | 匹配从a 到f范围内的任意一个字符 |

### 4：cd

|       |                   |
| ----- | ----------------- |
| cd    | 切换到当前用户的主目录       |
| cd \~ | 切换到当前用户的主目录       |
| cd .  | 保持在当前目录不变         |
| cd .. | 切换到上级目录           |
| cd -  | 可以在最近两次工作目录之间来回切换 |

