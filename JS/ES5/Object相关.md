

### Object.create 

     Object.create = function (o) {
       function F() {}   // 定义一个隐式的构造函数
       F.prototype = o 
       return new F()  // 本质还是通过 new 来实现
     }

 通过 Object.create() 方法，使用一个指定的原型对象和一个额外的属性对象创建一个新对象。
 这是一个用于对象创建、继承和重用的强大的新接口。说直白点，就是一个新的对象可以继承一个对象的
 属性，并且可以自行添加属性

### Object.create(null)

 使用 `null` 来创建一个新的对象，`null` 是没有任何属性和方法，继承了一个null,
 所以里面没有任何东西
 
### Object.freeze()
 
 冻结对象，不能给对象添加属性，不能更改属性值，不能删除指定的属性；
 不能修改属性的可枚举性，可配置性，可写性
 
 



