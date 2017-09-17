
## Flex布局

[阮一峰 Flex 布局教程-语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

### 背景

- 传统布局基于盒状模型 依赖 `display` | `position` | `float` 垂直居中不易实现

- 2009 W3C 未来首选

### 概念

 - Flexible Box 的缩写 ，弹性布局
 
 - 任何一个容器（包括行内）可指定 flex 布局
 
 - 设置后，子元素 float| clear | vertical-align 等失效
 
    
     // 块 
     .box{
       display: flex;
     }
      
     // 行内 
     .box{
       display: inline-flex;
     }
 
### 容器属性
     
容器有6个属性设置

- flex-direction

- flex-wrap

- flex-flow

- justify-content

- align-items

- align-content
     
#### 1、flex-direction
     
flex-direction属性决定主轴的方向（即项目的排列方向）     

    .box {
      flex-direction: row | row-reverse | column | column-reverse;
    }
     
 <div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071005.png">
 </div> 

它可能有4个值

- row（默认值）：主轴为水平方向，起点在左端

- row-reverse：主轴为水平方向，起点在右端

- column：主轴为垂直方向，起点在上沿

- column-reverse：主轴为垂直方向，起点在下沿
  
#### 2、flex-wrap  

项目都排在一条线（默认）上。flex-wrap属性定义，如果一条轴线排不下，如何换行

    .box{
      flex-wrap: nowrap | wrap | wrap-reverse;
    }
    
可能取三个值

##### 1、nowrap（默认）：不换行

<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071007.png">
 </div> 

##### 2、wrap：换行，第一行在上方

<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071008.jpg">
 </div> 

##### 3、wrap-reverse：换行，第一行在下方

<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071009.jpg">
 </div> 
 
#### 3、flex-flow 
    
flex-direction(1) 属性和 flex-wrap(2) 的简写，默认 row nowrap

    .box {
      flex-flow: <flex-direction> || <flex-wrap>;
    }
    
#### 4、justify-content     

定义了项目在主轴上的对齐方式

    .box {
      justify-content: flex-start | flex-end | center | space-between | space-around;
    }

<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071010.png">
</div>     

#### 5、align-items属性

项目在交叉轴上如何对齐

    .box {
      align-items: flex-start | flex-end | center | baseline | stretch;
    }
    
<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071011.png">
</div>      

#### 6、align-content属性

定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用

    .box {
      align-content: flex-start | flex-end | center | space-between | space-around | stretch;
    }
    
<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071012.png">
</div>     

### 项目属性

一共6个

- order

- flex-grow

- flex-shrink

- flex-basis

- flex

- align-self

#### 1、order属性

项目的排列顺序。数值越小，排列越靠前，默认为0

    .item {
      order: <integer>;
    }
    
<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071013.png">
</div>     
 
#### 2、flex-grow属性

定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大

<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071014.png">
</div> 

#### 3、flex-shrink属性

定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小

<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071015.jpg">
</div> 

#### 4、flex-basis属性

定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。
它的默认值为auto，即项目的本来大小

    .item {
      flex-basis: <length> | auto; /* default auto */
    }

#### 5、flex属性

flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选

    .item {
      flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
    }
    
该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。
建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值

#### 6、align-self属性
    
align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，
表示继承父元素的align-items属性，如果没有父元素，则等同于stretch    

    .item {
      align-self: auto | flex-start | flex-end | center | baseline | stretch;
    }
    
<div align=center>
    <img src="http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071016.png">
</div>    
    
