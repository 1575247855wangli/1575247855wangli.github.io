---
title: git
date: 2018-11-22 11:27:01
type: "tags"
tags: 
- git
category: git
description: "git常用命令"
---
- git init 
- git add 文件名 可以增加一个或者多个文件 
- git add . 添加所有文件
- git diff 查看和之前提交有啥区别
- git commit -m "描述"
- git log 查看历史记录
- $ git reset --hard 回滚
- HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
- git status 查看状态
- git remote add origin git@server-name:path/repo-name.git 把本地和线上github链接
- 使用命令git push -u origin master第一次推送master分支的所有内容；
- 要克隆一个仓库，首先必须知道仓库的地址，然后使用git clone命令克隆。
- $ git checkout -b dev == $ git branch dev  $ git checkout dev   创建分支并切换分支
- $ git branch 查看分支
- $ git checkout master 切换分支
- $ git merge dev 合并分支
- 创建+切换分支：git checkout -b <name>

- 合并某分支到当前分支：git merge <name>

- 删除分支：git branch -d <name>
- 查看分支：git branch

- 创建分支：git branch <name>

- 切换分支：git checkout <name>