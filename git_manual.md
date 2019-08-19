## 配置用户参数
```sh
	git config --global user.name "John Doe"
	git config --global user.email "1135317965.qq.com"
	git config --global core.editor emacs
	git config --global merge.tool vimdiff
	git config --global credential.helper store   // 保存用户名和密码
```

## 查看配置参数
```sh
	git config --list
	git config user.name
```

## 查看某条命令的帮助信息
```sh
	git help <verb>
	git <verb> --help
	example:git help config
```

## 将README文件添加到版本控制	
```sh
	git add README
```

# 文件移动(重命名)
```sh
git mv README.md README
```

# 更新远程代码(method 1)
```sh
git remote -v
git fetch origin master
git log -p master.. origin/master
git merge origin/master
```

## 更新远程代码(method 1)
```sh
git fetch origin master:temp
git diff temp
git merge temp
git branch -d temp
```


## 查看提交历史
```sh
git log
git log -p -2
git log --pretty=oneline
git log --pretty=format:"%h - %an, %ar : %s"
git log --since=2.weeks
```

## 查看单个文件提交历史
```sh
gitk --follow filename
```

## 修改最后一次提交
```
git commit -m 'initial commit'
git add forgotten_file
git commit -amend
```

## 取消已暂存的文件
```sh
git reset HEAD benchmarks.rb
```

## 取消对文件的修改
```sh
git checkout -- benchmarks.rb

git remote
git remote -v

git push origin master
git remote show origin
git pull 
git remote rename pb paul
git remote rm paul
```

## 标签
```sh
git tag
git tag -l 'v1.4.2.*'
git tag -a v1.4 -m 'my version 1.4'
git show v1.4
git push origin v1.0.0
git push origin --tags

git config --global alias.st status
git config --global alias.ci commit
git config --global alias.last 'log -1 HEAD'
```

## 使用HTTPS协议clone的情况下保存用户名和密码
```sh
git config --global credential.helper wincred
```


## 远程分支
### 删除远程分支
```sh
git push origin :<branch>
```
### 创建远程分支
首先在本地创建分支（示例中是从master分支创建），然后推送到远程分支，<branch>和<remote-branch>一般命名一致.
```sh
git checkout -b <branch> master
git push origin <branch>:<remote-branch>
```
### 关联远程分支
```sh
git branch --set-upstream-to=origin/<remote-branch> <branch>
```
### 合并远程分支
```sh
git merge origin/<remote-branch>
```
### 从远程分支分化一个本地分支
```sh
git checkout -b <branch> origin/<remote-branch>
```
### 查看关联的远程分支
以下三条命令均可查看
```sh
git branch -vv
git remote show origin
cat .git/config
```

## 本地分支
### 创建本地分支
```sh
git checkout -b <branch> <exist-branch>
```
### 删除本地分支
```sh
git branch -d <branch>
```
### 删除本地分支
```sh
git branch -d <branch>
```
### 删除本地分支
```sh
git branch -d <branch>
```

## 存储用户名和密码
```sh
git config --global credential.helper store
git config --global credential.helper wincred
```
## 回滚到指定版本
```sh
git reset --hard 'commit_id'
git push origin master --force
```

















