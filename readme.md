1.svn和git：版本控制器
  1.SVN:
    1.svn服务器默认是80端口
      为避免冲突，可以修改为8080端口
    2.创建仓库
    3.创建用户
    4.测试期间，关闭防火墙
  2.测试svn
    1.模拟两个用户：iwen和zhangsan
    2.iwen创建内容上传到服务器
      1.检出：关联服务器
      2.提交：将内容上传到服务器
    3.zhangsan检出内容
    4.zhangsan修改内容，提交到服务器
    5.iwen更新数据
  3.多人交互
  4.图标显示
    https://jingyan.baidu.com/article/4d58d541c819a89dd4e9c0e6.html
  5.版本冲突
    多人操作同一个文件，都执行上传操作，则会产生冲突

2.Git
  集中式：svn
  分布式：git
  1.安装：
    git config --global user.name "Your Name"
    git config --global user.email "email@example.com"
    自报家门
  2.创建仓库
    1.创建文件夹作为仓库
    2.初始化仓库：git init
    3.上传到仓库中
      git add filename
      git commit -m '注释'
  3.时光穿梭机
    1.查看git信息
      1.git status:命令可以让我们时刻掌握仓库当前的状态
      2.git diff:查看文件具体修改信息
    2.版本回退
      git log:查看提交的版本信息
      git reset --hard HEAD^
    注意：在执行完毕回退之后，在命令框不关闭的情况下可以在回来
    3.工作区与暂存区
      工作区 ->(add) ->暂存区 ->(commit) 版本库
    4.删除文件
      git rm 文件名
      在版本库中未删除情况下恢复：git checkout vnum filename
      注意：谨慎操作
  4.分支管理
    1.创建分支并切换到分支
      git checkout -b dev
    2.合并子分支
      git merge dev
    3.切换分支
      git checkout master
    4.删除分支
      git branch -d dev
    5.查看分支
      git branch
    6.解决冲突
      手动解决，将子分支与主分支代码合并，在提交代码
  5.github托管代码
    1.创建SSH Key
      ssh-keygen -t rsa -C "youremail@example.com"
    2.登陆GitHub，打开“Account settings”，“SSH Keys”页面添加SSH KEY
    3.将代码推送到github托管
      1.关联github：git remote add origin https://github.com/sxtiwen/web1711.git  （只有第一次推送需要执行）
      2.推送到github：git push -u origin master
    4.修改代码之后继续推送
      1.将代码重新提交到版本库
        git add
        git commit
      2.git push
