
## 淘宝镜像

    npm install -g cnpm --registry=https://registry.npm.taobao.org

## git 删除远程仓库文件

使用 git rm 命令

- `git rm --cached` “文件路径”  从缓存中将文件删除 不删除物理文件

- `git rm --f` “文件路径”  缓存、物理全部删除

## 使用 git checkout命令

     `git checkout` 版本号 ： 用来在本地切换对应的版本
     
     例如 `git checkout online`
 
## git放弃本地修改 强制更新

      git fetch --all
      git reset --hard 最新版本
      
## git 查看远程仓库地址
      
      git remote -v
    
## git 提交版本分支
    
      git push --set-upstream origin 版本号

## 查看本地分支

     git branch -l 

## 查看远程分支

     git branch -r 

## 查看全部分支（远程的和本地的）

     git branch -a 

## 创建并切换到分支feature-branch  

    $  git checkout -b feature-branch    

##  推送本地的feature-branch(冒号前面的)分支到远程origin的feature-branch(冒号后面的)分支(自动创建)
    $  git push origin feature-branch:feature-branch    

## git配置工程的use.name和user.email

    $ git config –global user.name “github’s Name”

    $ git config –global user.email “github@xx.com”

    $ git config –list
