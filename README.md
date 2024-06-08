

# Github使用手册

## 搜索

关键字查询 **awesome** ，去此标签类别中查询项目 
**python tutorial** ，查询资料，书籍，文档 
**socket sample** ，查询对应技术的代码样例

## Github 三要素 

### Repository 仓库 

仓库是github项目管理存储基本单位 一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库分为public ,private 

### Commit 提交

程序员在整个开发周期，有大量的对代码资源的迭代和修改，都可以通过commit 的方式进行记录，便于程序员回溯代码，即是这些代码被删除提交便于使用者观察整个工程的开发流程以及设计流程 

### Branch 分支 

在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，默认的仓库主分支为master /main 
**不仅可以管理代码存储，便于多人协作开发** 

![示例图片](https://i.postimg.cc/9Q9ZZz9z/1717768324861.png) 

## 仓库内容

**Code**，资源存储，代码资源，二进制，项目管理脚本，许可证等等
**issue**，使用时遇到的bug 或 进行提交 ，等待反馈
**README**，使用markdown语言编写，工程自述文件，开发进度，版本更新，使用介绍等等
**LICENSE**，许可证
GPL 2.0 3.0
Apache 2.0  ， Mit，这些许可证，给使用者最大使用权限以及最少的限制

## Git软件，分布式版本控制系统

**仓库管理软件，使用git管理私人代码或企业代码** 
![1717769604449](https://i.postimg.cc/SNZg7Ttv/1717769604449.png)

本地的版本比云端的版本要更新

## 设备认证

### 1.如何让网站的账户与设备绑定，后续完成代码的管理，上传下载 

```bash
git init #创建本地仓库           *后续对仓库的操作，都要在仓库位置(master) 
```

![1717773867624](https://i.postimg.cc/Nj5pN63f/1717774071407.png)

```bash
git config --list  #查看git的配置文件 
```

![1717773962880](https://i.postimg.cc/FH8Gwfvb/1717773962880.png)

#### 添加config配置项

```bash
git config --global user.email "邮箱地址"
git config - -global user.name "Github用户名"       SSH远程访问 
```

#### 生成本机设备密文

```bash
ssh-keygen -t rsa- C "注册邮箱" #创建本地密文  去对应的目录查找密文文件
```

**rsa.pub**复制密文，粘贴**settings ->SSH key and GPG ->new ssh key ->粘贴** 
![1717774267492.png](https://i.postimg.cc/sX9cBwhK/1717774267492.png)

#### 检验是否关联成功

```bash
ssh -T git@github.com
```

![1717774330582](https://i.postimg.cc/7Z3frd8B/1717774330582.png)

### 2.为目标仓库起别名，定位目标仓库，后续上传

```bash
git remote add origin(别名) "ssh 地址"(云端仓库地址) #为ssh仓库地址创建别名为origin 
git remote remove origin #删除origin 别名 
git remote add orgin "ssh地址" #为ssh仓库地址创建别名为origin 
```

## 本地设备与云端仓库的交互逻辑 

![1717770939183](https://i.postimg.cc/pyNXgY0b/1717770939183.png)

```bash
git add 文件名 #添加内容到git缓冲区
git rm#删除本地文件并删除仓库数据
git restore code.c#恢复误删除文件(仓库存在)
```

#### 推送到GitHub

![1717774811865](https://i.postimg.cc/MZn0J6sd/1717774811865.png)

![1717774893559](https://i.postimg.cc/hPx9hCRm/1717774893559.png)

```bash
#将本地代码添加到git缓冲区
git add code.c

#将缓冲区代码提交到本地仓库
git commit  
git commit -m "备注信息" #生成提交记录

#将本地仓库内容推到云端仓库
git push origin(云端仓库地址) master
```

```bash
git status #查看状态
```

![1717775333693](https://i.postimg.cc/pLJzJpTX/1717775333693.png)

## 代码更新的依赖关系被破坏

本地内容要比云端新，完成更新替换，但是如果直接修改云端内容，导致本地内容无法再次提交 

![1717775389598](https://i.postimg.cc/CKv89Xk3/1717775389598.png)

**先拉取gitpull 云端内容与本地内容合并或操作，而后再次推即可** 

![1717775404437](https://i.postimg.cc/Y9hF7Rxh/1717775404437.png)

```bash
git pull - -rebase origin master
git rebase --skip "忽略本地内容保留云端内容" 
git rebase --abort "忽略本地内容保留云端内容" 
git rebase --continue "忽略本地内容 保留云端内容"
```

## 下载开源代码

```bash
git clone "https 仓库地址" #下载开源项目code资源 
```

## 分支Branch 

**关于分支的相关命令，创建分支、选择分支、合并分支等等** 

## Markdown 语言

github 可以编写readme ，文本修饰语言

Markdown,文本修饰语言，用符号显示文本特殊效果<br>

# 标题修饰符（一级标题）

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

换行用\<br\>标签实现

## 正文内容

这是一段测试文本

重点显示文本，`重点显示`，用\`\`实现

*test txt*

**test txt**

***test txt***

~~test txt~~

![1717773510046](https://i.postimg.cc/SKtXg8pq/1717773510046.png)

## 分割线

分割线用\-\-\-表示

------

## 引用\>

> 一级引用
>
> > 二级引用
> >
> > > 三级引用

![1717773545421](https://i.postimg.cc/hjzX6jSm/1717773545421.png)

## 列表

### 有序列表

1. 物理学
   1. 粒子物理
   2. 原子核物理
   3. 力学
2. 计算机科学
   1. 分布式架构
   2. 云计算

### 无序列表

- 二次元游戏
  - 原神
- 大逃杀游戏
  - PUBG
  - APEX

### 混合列表

1. 计算机科学
2. 分布式架构

- 云计算

1. 物理学

- 粒子物理

1. 原子核物理

![1717773614058](https://i.postimg.cc/XvhJfbwY/1717773614058.png)

## 表格\|

| 名称 | 能力 | 排行 |
| ---- | :--: | ---: |
|      |      |      |
|      |      |      |
|      |      |      |

![1717773634653](https://i.postimg.cc/ry9TcTKR/1717773634653.png)

--表示居左对齐
:--:居中对齐
--:居右对齐

## 代码片段

在\`\`\`

\`\`\`内插入代码片段，和对应的语言版本

```c
	#include<stdio.h>
	int main()
	{
	   printf("测试代码\n");
	   return 0;
	}
```

```cpp
	#include<iosream>
```

```python
	import <os>
```

```bash
  	ls -l
	ps -aux
```

## 超链接

超链接插入格式：
\[  ] \(    "悬浮文本")

[Github](https://github.com/ "点击访问")

## 插入图片

!\[   ]( )

