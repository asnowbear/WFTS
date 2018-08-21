

### Webpack 和 grunt 和 gulp 有啥不同

Webpack是一个模块打包器，grunt和gulp是执行任务的，webpack可以递归的打包项目中的所有模块（递归：指定一个入口，分析模块的依赖，它会递归的查找所有相关的依赖），最终生成几个打包后的文件，他和其他的工具的最大的不同在于它支持code-splitting（代码分割），模块化（AMD，ESM，CommonJS）开发，全局的分析工具（分析整个项目引入的模块）

### 什么是 bundle，什么是 chunk，什么是 module

bundle是由webpack打包出来的文件，chunk是指webpack在进行模块依赖分析的时候，代码分割出来的代码块，module是开发中的单个模块

### 什么是 loader，什么是 plugin

loader是用来告诉webpack如何转化处理某一类型的文件，并且引入到打包出的文件中
plugin是用来自定义webpack打包过程中的方式，一个插件是含有apply方法的一个对象，通过这个方法可以参与到整个webpack打包的各个流程（生命周期）

### webpack-dev-server 和 http 服务器如 nginx 有什么不同

webpack-dev-server使用内存来存储webpack开发环境下的打包文件，并且可以使用模块热更新，他比传统的http服务器对开发更加简单高效

### 什么是模块热更新

模块热更新是webpack的一个功能，他可以使得代码修改过后不用刷新浏览器就可以更新，是高级版的自动刷新浏览器（将代码重新执行而不整体刷新浏览器）