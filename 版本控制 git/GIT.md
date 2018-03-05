
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

