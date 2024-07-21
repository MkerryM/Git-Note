# Git

工作区 （本地文件夹目录）

暂存区 （当前修改过的操作放入暂存区）

版本库（暂存区的放入版本库 通过commit）

```bash
git config --global user.name yxc
git config --global user.email yxc@qq.com #(与git同步)
vim .gitconfig #查看修改
```

```bash
#当前目录创建仓库
git init 
#将XX添加到暂存区 状态变化一次 都要使用此条命令
git add XX 
#所有修改文件添加暂存区
git add .
#查看修改后的文件是否加入暂存区 红 绿 两种状态
git status 
#将暂存区内容添加到仓库 备注位"XX" 然后暂存区删除
git commit -m "备注"
#比较暂存区的文件 与 之前提交的文件之间的区别 会额外标注出来
git diff XXX 

#将某文件踢出版本控制的管理范围(文件还在) git add重新加入 ****
git rm --cached XX 
git restore --staged XXX#还在管理范围内 只是移除暂存区的更改 工作区的不变
git restore #撤销工作区修改 暂存区不变

#查看历史版本 从下往上返回各个版本
git log 
#显示在一行
git log --pretty=oneline
#一个^返回一次版本
git reset --hard HEAD^ 
#结尾跟编号 返回特定版本 哈希值前7位
git reset --hard XXXX  
#显示head所有记录 指针移动记录
git reflog 

#撤销工作区修改 暂存区不变
git restore XXX  或 git checkout - XX
1工作区修改了，没有加入暂存区 实现清空修改操作
2工作区修改了，上次的已经加入暂存区 还原暂存区内的版本 

#当你想要取消某个文件的暂存状态，但又不想丢失工作区中对这个文件的更改时
#先执行 如果工作区没东西 退到工作区 如果工作区有同样文件直接删除 不改变工作区内容
git restore --staged XXX
git restore XXX 

#创建分支
git branch XXX
#查看所有分支和当前所处分支
git branch 
#切换到XXX分支
git checkout XXXX
#创建并切换
git checkout -b XXX
#将XX合并到当前分支
git merge XXX 
#删除本地XXX分支
git branch -d XXX

#将本地仓库映射到远程云端仓库
git remote add origin XXX
#克隆到本地
git clone XXX
#将当前分支推到云端
git push -u
#本地同步到云端
git push --set-upstream origin XXX 
#删除云端分支
git push -d origin XXX  
#将云端分支拉取到本地
git checkout -t origin/XXX
#先需要绑定
#将远程"当前分支"与本地"当前分支"合并 同一个文件
git pull
#将远程"XXX"分支与本地"当前“分支合并（同步到本地）
git pull origin XXXX

```



