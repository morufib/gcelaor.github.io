

#Github创建项目demo

layout:     post
title:      "Github创建项目demo"
subtitle:   "Created-A-Demo-In-The-GitHub"
date:       2016-11-7 22:09:15
author:     "Gcelaor"
header-img: "img/Responsive.jpg"
catalog: true
tags:

    - Git
    - Github



##正文
```
   假设我们GitHub 仓库中已经有了分支 gh-pages（仓库中Setting—成功预览—GitHub Pages）

   注意：我们生成Github Pages的目的就是需要生成一个gh-pages分支(咱们正常情况下只有一个master分支)
```

###GitHub仓库中clone你的项目到本地仓库

```
git clone https://github.com/user/repository.git
# Clone our repository
Cloning into 'repository'...
remote: Counting objects: 117, done.
remote: Compressing objects: 100% (81/81), done.
remote: Total 117 (delta 29), reused 117 (delta 29), pack-reused 0
Receiving objects: 100% (117/117), 484.54 KiB | 8.00 KiB/s, done.
Resolving deltas: 100% (29/29), done.
Checking connectivity... done.
```

###切换到本地仓库（Repository）目录下

```
   cd Repository
```

###将分支切换到gh-Pages

```
   $ git checkout gh-pages（将master分支切换到gh-pages分支上）
```

###移除旧工作树中的所有文件，只保留.git

```
   git rm -rf .
   # 移除旧工作树中的所有文件
   rm '.gitignore'
```

###添加demo内容相关的文件到gh-pages，push到GitHub

```
   git add . （将本地所有文件加到仓库里） 
   git commit -m "message" （设置提交信息） 
   git remote add origin git@github.com:Your_Name/Repository.git（本地仓库链接远程仓库） 
   git push -u origin gh-pages （push文件到仓库中）
```

###预览demo地址

https://gcelaor.github.io/Responsive-Web/index.html

```
   gcelaor为我的GitHub用户名
   Responsive-Web我的仓库
   index.html预览的demo文件
```
