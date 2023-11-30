# GitHub入门速通教程

## 什么是Github？
GitHub是一个提供版本控制和协作开发的代码托管平台，可以让你和其他人在任何地方一起开发项目。

## 为什么要用Github？
Github目前已经是最流行的开源项目托管平台，我们可以在GitHub找到很多有用的代码，学习某项技术，甚至帮助开发某个项目。对于学习深度学习的开发者，无论是深度学习框架，还是最前沿的深度学习算法，通常你都能在GitHub上找到其源代码并帮助你的研究和开发工作。

## 什么是Git？
Git是一个版本控制系统，使用Git的项目（无论是否在Github上）可以得到更好的版本管理，便于对项目做开发、修改、还原和发布等。

我会把Git理解为一些帮助我实现版本控制的命令行工具，使用这些命令可以实现对项目内容的增删查改并保留完整的记录。

Git是由著名的Linux之父Linus Torvalds在2005年开发

3# Github的基本概念
1. 仓库（Repository）
仓库(Repository)，简称Repo，通常用来管理和存放一个单独的项目，在本文中也称作”项目“。一个Repo中可以包含文件、文件夹、图片、视频、表单任何项目需要的文件。

一个Repo通常需要一个READMD文件，我们推荐使用markdown格式的文本文档来说明项目相关的信息。

2. 本地(local)和远程(remote)
如果，（1）我们创建了一个本地项目，然后我们将其push到github上自己的账户中；（2）或者我们在github账户中（通过浏览器）创建了一个repo，又将其pull到本地。

此时在local和remote会分别存有两份项目的拷贝。这两份拷贝既独立又有联系，我们可以通过一些git命令是他们之间相互“推送”代码和文件。也就是说，当你在本地修改项目内容时，远程的repo是不会知道这些修改的，直到这些修改被push到remote，远程repo中的代码才会被更新。

3. 分支 (branch)
分支可以让我们在项目Repo中处理多个不同的版本，默认情况下，项目会有一个默认分支main (有些项目的默认分支是master)。

我们通过创建分支来开发和修改项目，然后再将这些修改提交并入到main分支。

当你基于main分支创建一个新的分支时，可以理解为我们现在有了一个main分支的拷贝，或者叫snapshot，这份拷贝是基于main分支此时当前状态下的“复制”。要注意，当你在新的分支进行开发时，如果其他人对main分支进行了修改，你可能需要拉取(pull)这些更新的内容到你的分支里。

分支的一个重要作用是协同开发，在GitHub上，很多项目的开发人员都是通过创建新的分支，来修复bug，开发新的功能，或者开展新的尝试，当相关工作完成之后，这些修改将会合并（merge)到main分支上。

4. 提交（commit）
对Github的项目进行修改，叫做commit。每一条commit都会附带一条commit信息，用来记录这条修改的简要描述，例如，“修复了某个bug” 或者 “增加了某个功能”。commit本身会记录对项目修改的所有内容。

使用Commit命令前，我们通常需要使用add命令，将修改或增加的项目文件“添加”到git中，让git能够跟踪到这些文件，例如我们在项目中修改了README.md文件，在commit之前：

git add README.md
我们还可以通过git status来查看文件状态，用以确定哪些文件需要添加，完成添加后，使用commit命令完成此次提交：

git commit -m 'update readme file'
其中-m参数用来添加commit message，建议使用简洁的客观描述概括本次commit的主要内容。

5. 拉取请求 (Pull Request)
拉取请求（Pull Request）又称作PR，是在github上进行合作开发的核心概念。当你提交一个PR，表示你提议将自己对项目的修改并入到别人项目中的某一分支里去。这个提议将由对方项目的相关人员进行审核，然后完成并入(merge)操作。当然，你也可以在自己项目中提交PR，并自己并入自己的分支。

6. Fork
Fork通常是指拷贝一个repo，这个repo可以作为你要修改、贡献该项目的起点，或者作为你自己项目的一个组件。

如果你在（别人的）项目中发现了一个bug，并且要修复它，那么你可以做：

Fork这个项目
修复bug
提交PR给项目
通常我们可以方便的在浏览器中使用Github的fork功能，当Fork完成之后，在我们自己的GitHub账户下，就多了一个forked repo。

7. 克隆（Clone）
通常情况下，我们在将项目从远程(github网站)拷贝到本地进行使用或者修改，可以使用clone功能。例如，我们想要将PaddleViT项目拷贝到本地，可以在命令行中使用以下命令：

- git clone https://github.com/BR-IDL/PaddleViT.git
当远程项目有更新时，我们不需要再次clone，只需要使用pull命令，可以将远程repo的更新内容拉取到本地项目中来:

- git pull
如果是我们创建的远程repo，在本地进行修改(并commit)之后，我们可以使用push命令将这些更新，上传到远程repo中：

- git push
注意： 如果我们clone的是别人的项目，通常只有pull权限，而不能push，如果想要修改别人的项目，可以使用fork + clone + push + PR的方式。

7. 星标（Star）
仓库的书签或者赞赏表示。Star是项目受欢迎程度的表示方式。

如果您觉得本教程对您有帮助，请支持我们的项目Here为我们点Star，感谢您的支持！

# 如何使用Github上的开源项目
## Case 1. 我希望使用某个项目
将项目git clone到本地
使用项目
如果远程Repo有更新，使用git pull拉取更新
## Case 2. 我希望修改或者为某个项目增加功能
将远程Repo fork到自己的github中，这一步可以在github网站页面完成
将forked之后的项目拷贝git clone到本地
在本地完成修改或者开发，并commit这些修改
将本地修改git push到远程forked repo中
给项目提交PR（可以使用github网站页面完成）
项目相关人员会审核代码、给反馈或者提出修改，无误后并入项目Repo
## Github使用示例
下载并开始使用PaddleViT项目:

在命令行中clone项目到本地：

git clone https://github.com/BR-IDL/PaddleViT.git
安装相关依赖，例如Paddle2.1等

# 使用项目

参与PaddleViT项目的开发：

ForkPaddle项目：在项目Github主页（https://github.com/BR-IDL/PaddleViT）右上角点击"Fork"按钮

Fork成功页面将跳转至用户自己的Github Repo，点击Code按钮并复制项目Clone地址

使用上一步复制的地址，在命令行中clone项目到本地：

git clone https://github.com/YOUR_ACCOUNT/PaddleViT.git
进入项目文件夹并创建新branch，默认会基于develop分支创建新分支：

git checkout -b YOUR_BRANCH_NAME
YOUR_BRANCH_NAME 通常为所做任务的名称，例如“swin_bug_fix”, 'XYZ_model'等

# 完成开发

完成commit

- git add . #这一条将添加当前目录下所有文件，也可根据实际情况添加需要的文件
git commit -m "YOUR_COMMIT_MESSAGE" # message 尽量简洁明了
将代码push到远程

- git push origin YOUR_BRANCH_NAME # origin通常指向本地代码在Github上的远程版本
创建PR

- 在GitHub项目页面，点击Pull Request Tab
点击New pull request, 选择Forked Repo的分支和目标推送到的项目分支
点击Create pull request