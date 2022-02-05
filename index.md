# Welcome to git learning record

Git 当前最强大的分布式版本控制系统

不仅仅是简单的复制粘贴，他保存了提交的历史记录，这也是为什么大多数提交记录的上面都有父节点的原因

# 本地建库：
## 1.首先得自报家门

git config --global user.name "Your Name"

git config --global user.email "email@example.com"
## 2.其次得有仓库（repository），有两种
自己找个文件夹建立仓库：

mkdir learngit（这是名字）

cd learngit

pwd(显示仓库目录)

git init(变成可以管理的仓库)，也可以直接在文件夹内打开git bash，输入git init
## 3.有仓库之后，添加和提交到仓库（git自动创建master分支）

添加：git add  .py 从工作区添加文件到暂存区

提交：git commit -m "干了什么改动" 从暂存区提取出来master

git status 随时查看状态

git diff可以知道到底改了什么
## 4.如何在不同历史版本之间任意穿梭

git log 用来查看所有信息，commitid很重要，尤其前五位

当前版本为HEAD，返回上一个版本：git reset --hard HEAD^

再要返回当前版本：git reset --hard 1111a(id前五位)

万一关闭了窗口，可以用：git reflog 记录每一次操作
## 5.撤销修改
### 1 工作区修改了还没有add
git restore .py
### 2 工作区修改了而且add了
git reset HEAD .py

git restore .py
## 6 删除与恢复
git rm .py

误删修复：

git checkout --  .py(只要库里添加提交过了)


# 远程建库：
## 1.创建公钥和私钥
windows下打开git：ssh-keygen -t rsa -C "youremail@example.com"

创建完成后，输入：

cat ~/.ssh/id_rsa.pub 获取公钥，私钥保存好
## 2.github创建SSH Key
复制粘贴
## 3.创建远程库
### README文本不创建（建议）

git remote add origin git@github.com:NoMoreHesitation/learngitsecond.git（SSH路径，自己查找，https也可以略复杂）

完成之后，即可用指令：

git branch -M main(本地建立分支库main)

git push -u origin main 第一次输送到github(origin名字是规范，也可以换名字)

git push origin main 后面几次
### README文本已经创建
建立main分支后：

git pull --rebase origin main

git push origin main
# 从远程库克隆
选择一个文件夹：
git clone git@github.com:NoMoreHesitation/learngitsecond.git
# 早建分支，早用分支
## 1.为何建立分支
主线任务可以先停滞，但时间不等人，可以先开支线任务，最后合并在一起，删掉支线任务，经验还是不落下！
## 2.建立分支
创建加切换：如果master是空的，则会删除master
最新版本：
git switch -c aaa

老版本：
git checkout -b aaa(创建并转到aaa分支，不再是master，HEAD指向aaa)
相当于：

git branch aaa

git checkout aaa

## 3.查看分支

git branch

## 4.正常添加提交后,合并任务，增加经验：

git checkout master

git merge aaa
## 5.删除分支
git branch -d aaa 
# 团队协作
![image](https://user-images.githubusercontent.com/96240580/152651767-f6a49bb7-32ea-43ac-848f-bd6bc0f5b7ca.png)
## master主分支不要动，每个人在自己的分支干活
## 两种合并方法：
### 1.fastforward:
git merge dev

![image](https://user-images.githubusercontent.com/96240580/152651870-db544e90-ddde-41db-bcfe-f96a74dc2a6a.png)

### 2.禁用ff方法，可以看分支历史
git merge --no-ff -m 'merge with no-ff' dev

![image](https://user-images.githubusercontent.com/96240580/152651904-30d4e52c-3886-4597-b35b-5cd645f2cdf3.png)

## 工作区消失术（修复bug）

git stash

建立分支修复bug，然后add commit，删除分支

git stash pop

master修复的bug应用于aaa分支

git checkout aaa

git cherry-pick 改动对应的id


# 其他指令
git branch XX 用于在当前节点建立分支XX

git checkout XX  用于切换分支到XX

git merge 用于合并两个分支

git rebase 也用于合并，“线性”合并分支

git checkout 直接引用
HEAD 是一个对当前检出记录的符号引用

git checkout main^  一个^ 符号表示向父辈移动一位

git reset 本地撤销操作

git revert 共享撤销操作

git cherry-pick 需要复制的节点到当前节点

git rebase -i 从新的图窗人工具体操作
