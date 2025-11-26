# Git 简明手册

## 配置

### 配置用户信息

配置个人的用户名称和电子邮件地址，这是为了在每次提交代码时记录提交者的信息

```bash
git config --global user.name "runoob"
git config --global user.email "test@runoob.com"
```

如果用了 --global 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。

如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 --global 选项重新配置即可，新的设定保存在当前项目的 .git/config 文件里。

### 查看配置信息

要检查已有的配置信息，可以使用 git config --list 命令

## 生成 SSH 密钥（可选）

如果你需要通过 SSH 进行 Git 操作，可以生成 SSH 密钥并添加到你的 Git 托管服务（如 GitHub、GitLab 等）上。

```bash
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
```

## 初始化仓库

### 一个新的 Git 仓库

```bash
git init
```

### 克隆现有仓库

```bash
git clone <仓库地址>
```

## 添加和提交更改

### 将文件添加到暂存区

```bash
git add <文件名>   # 添加指定文件到暂存区
git add .  # 添加所有文件到暂存区
```

### 提交更改到本地仓库

```bash
git commit -m "提交信息"
```

## 分支管理

### 创建并切换到新分支

```bash
git checkout -b <分支名>
```

### 切换回主分支

```bash
git checkout master
```

### 删除分支

```bash
git branch -d <分支名>
```

## 推送到远程仓库

### 首次推送时需添加远程仓库

```bash
git remote add origin <远程地址>
git remote add origin https://github.com/chenjunhui/brief_manual.git
git push -u origin master
```

推送到远程仓库时，需要指定远程仓库的名称，默认是 origin。

### 将本地更改推送到远程仓库

```bash
git push origin <分支名>
```

### 远程仓库删除分支

```bash
git push origin --delete <分支名>
```

## 更新与合并

### 从远程仓库拉取最新更改并合并

pull 命令是从远程仓库拉取最新代码并自动合并到本地分支。
pull = fetch + merge

```bash
git pull
```

### 将其他分支合并到当前分支

```bash
git merge <分支名>
```

## 标签管理

### 为特定提交创建标签

```bash
git tag <标签名> <提交ID>
```

### 查看提交历史以获取提交 ID

```bash
git log
```

## 撤销更改

### 丢弃工作目录中的更改

```bash
git checkout -- <文件名>
```

### 重置本地分支到远程最新状态

```bash
git fetch origin
git reset --hard origin/master
```

### 查看远程仓库与本地仓库的对应关系

```bash
git remote -v
```

```bash
origin  <远程仓库地址> (fetch)
origin  <远程仓库地址> (push)
origin  https://github.com/chipweinberger/flutter_blue_plus.git (fetch)
origin  https://github.com/chipweinberger/flutter_blue_plus.git (push)
```

<br><br>

***
Markdown 简明手册
***

## 标题

### 子标题

#### 子子标题

##### 子子子标题

## 段落

正常文本

## 列表

无序列表‌：使用星号

* 项目 1
  * 子项目 1
  * 子项目 2
* 项目 2
  * 子项目 1
  * 子项目 2

有序列表：使用数字加句点加空格，如 1. 项目 或 2. 项目

1. 项目 1
2. 项目 2

## 任务列表

* [ ] 未完成任务 1
* [ ] 未完成任务 2
* [x] 已完成任务 1
* [x] 已完成任务 2

## 文本样式

**加粗**
*斜体*
~~删除线~~

## 图片

图片：![图片描述](https://i-blog.csdnimg.cn/blog_migrate/8f1b213356ed81d5a706d52c6ab7cb6d.png)

## 代码块

三反引号（```）是最常用的代码块语法，支持语法高亮和多行代码展示。

```text
文本块，没有语法高亮。
```

```javascript
$(document).ready(function () {
    alert('RUNOOB');
});
```

```python
def hello_world():
    print("Hello, World!")
```

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>
Hello, World!
</body>
</html>
```

```css
body {
    background-color: lightblue;
}
```

## 引用

Markdown 区块引用是在段落开头使用 > 符号 ，然后后面紧跟一个空格符号：
> 区块引用
> 菜鸟教程
> 学的不仅是技术更是梦想

多级嵌套引用
另外区块是可以嵌套的，一个 > 符号是最外层，两个 > 符号是第一层嵌套，以此类推：
> 最外层
> > 第一层嵌套
> > > 第二层嵌套

## 公式

公式：$E=mc^2$

## 表格

| 表头 1 | 表头 2 |
| ------ | ------ |
| 单元格 | 单元格 |
| 单元格 | 单元格 |

| Column 1 | Column 2 | Column 2 |
|:--|:--:| --:|
|  文本居左 |  文本居中 |  文本居右 |

## 分割线

---

## 链接

[菜鸟 Markdown 教程](https://www.runoob.com/markdown/md-tutorial.html)
