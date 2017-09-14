
## Flex布局

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
    
    