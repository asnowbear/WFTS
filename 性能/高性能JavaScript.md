
# 高性能JavaScript
> High Performance JavaScript For Building 
> Faster Web Application Interfaces

## JavaScript产生背景

- 96年[网景](https://baike.baidu.com/item/网景/70176?fromtitle=netscape&fromid=2778944&fr=aladdin)
（Netscape）发明，Netscape Navigator浏览器

- 改善网页的用户体验，并做简单的表单校验

## 为什么要优化性能

- [IE6](https://baike.baidu.com/item/Internet%20Explorer%206?fromtitle=IE6&fromid=8680416)的落后
   
     内存回收与web发展

- JS引擎落后-解释器
     
     [解释器与编译器](https://zhidao.baidu.com/question/17412751.html)

- 08年V8的出现
    
     通过把代码转成机器码
      
- 动态多层的web application导致

     网络延迟，影响页面的操作
      
## 方法有哪些

### 1、加载和执行

- CSS放顶端，JS放底部

  * 单线程运行，阻塞特性

- 合并脚本，减少请求

  * http请求消耗性能和时间开销
  
  * 1个100K的文件的时间 < 4个25K的文件加载时间

- 使用无阻塞下载JavaScript

   * 使用script标签的defer属性
   
       `<script type="text/javascript" defer="defer">`

   * 在window.onload后动态插入JS文件

   * 使用懒加载库类：LazyLoad、LAB.js 

### 2、数据存取

- 访问字面量和局部变量最快，数组元素和对象成员较慢

  * 存储位置造成

- 访问局部变量最快，访问全局变量最慢

  * 全局作用域链和局部作用域链
  
             function func() {
                var num = 1;
                alert(num);    
             }
             
            func();
            
             
   <div center>
   <img src="https://images0.cnblogs.com/blog2015/683414/201504/141726296825815.png"></img>
   </div>
  
- 闭包会引起性能问题，减少使用

  * 内存不释放
  
           function E() {
              var id = 1
              document.getElementById('save').onclick = function(e){
                saveDocument(id)
              }
            }

- 属性或者方法在原型链中位置越深，访问越慢

  * 原型链
  
    <div align=center>
       <img src="https://segmentfault.com/img/bVco7f"></img>
    </div>

- 缓存对象成员、数组元素、跨域变量

  * 减少寻找次数

### 3、DOM编程

脚本执行DOM代价昂贵，最常见的性能瓶颈

- 减少DOM访问次数，尽可能在JS端处理

   * ES和DOM想对独立的api，访问需要桥接

- 多次访问Dom变量，使用局部变量缓存

        function a () {
          var name = ''
          for (var i = 0;i < 1000; i++) {
            name = document.getElementsByTagName('div')[i].nodeName
            name = document.getElementsByTagName('div')[i].nodeType
            name = document.getElementsByTagName('div')[i].tagName
          }
        }

- 谨慎使用HTML集合对象，缓存集合length属性

  * 集合如

        document.images
   
        document.getElementsByName()
        
        document.froms[0].elements
        
  * 集合反映底层文档当前状态
  
        var divs = document.getElementByTagName('div)
        for (var i = 0;i < divs.length; i ++)  {
          document.body.appendChild(document.createElement('div'))
        }        

- 使用更快的API，典型的如 querySelectorAll()和firstElementChild

- 减少重排和重绘，使用批量修改样式，""离线"操作DOM树对象

  * 增加、删除可见dom元素
  
  * 改变元素位置
  
  * 元素尺寸改变（margin/padding/border/width/height） 

- 使用事件委托来减少事件处理器的数量

### 4、算法和流程控制

- 原生for循环最快，嵌套forEach其次,jquery.each最慢

- 逆序循环比正序循环快

- switch比if-else快，少条件是用if-else,多的话用switch

- if-else优化，将最可能出现的条件放在首位

- 优化递归，采用Memoization方式来缓存上次计算结果，避免重复计算

  * 例如：八方向搜索算法的优化

### 5、UI响应

- 避免写长时间(100ms)运行的Js

- 使用定时器来分割长时间的js代码执行

- 使用 requestAnimationFrame来代替定时器做动画

   * 避免过度重绘，浏览器做了动画优化
   
   * 尤其是 mousemove 或者 scroll

- 使用Web Workers来处理

   * 允许UI线程和JavaScript线程并行

### 6、Ajax优化

 - GET请求可缓存数据
 
 - 设置请求头信息，Expires
 
 - 使用本地缓存策略

 - JSON数据格式压缩

## 结尾

#### 实践

#### 平衡

#### 了解运行原理

