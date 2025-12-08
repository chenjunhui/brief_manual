# Git 简明手册

## 配置

### 配置用户信息

配置个人的用户名称和电子邮件地址，这是为了在每次提交代码时记录提交者的信息

```bash
git config --global user.name "chenjunhui"
git config --global user.email "chenjunhui@126.com"
```

如果用了 --global 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。

如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 --global 选项重新配置即可，新的设定保存在当前项目的 .git/config 文件里。

### 查看配置信息

要检查已有的配置信息，可以使用 git config --list 命令

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

### 将其他分支合并到当前分支

```bash
git merge <分支名>
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

>git push -u origin master‌ 是将本地master分支推送到名为origin的远程仓库，并建立分支追踪关系的Git命令。
>>git push -u origin master命令解析：
>>该命令由以下核心要素组成：
>>-u‌：设置上游关联（upstream），后续推送可直接使用git push简化操作。‌
>>origin‌：默认远程仓库名称（可通过git remote -v查看）。‌
>>master‌：本地分支名称，推送后会与远程同名分支建立映射关系。‌

### 将本地更改推送到远程仓库

```bash
git push origin <分支名>
git push origin # 省略分支名，则推送当前checkout的分支
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

## github 设置密钥

### 生成 SSH 密钥

如果你需要通过 SSH 进行 Git 操作，可以生成 SSH 密钥并添加到你的 Git 托管服务（如 GitHub、GitLab 等）上。

```bash
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
```

### 添加 SSH 密钥到 GitHub

登录 GitHub 并访问 Settings -> SSH and GPG keys -> New SSH key。

将生成的公钥(~/.ssh/id_rsa.pub)内容复制到 Key 文本框，并添加一个 Title（如“GitHub 密钥”）。

点击 Add SSH key 按钮完成添加。

### 测试 SSH 连接

```bash
ssh -T git@github.com
```

如果能成功连接，说明 SSH 密钥配置成功。

### 配置第二台电脑

如果要在另一台电脑上使用同样的 SSH 密钥，需要将公钥添加到 GitHub 账户中。

将 ~/.ssh/id_rsa复制到另一台电脑的 ~/.ssh/目录下。第一次使用时会询问是否信任该密钥，输入 yes 确认。
