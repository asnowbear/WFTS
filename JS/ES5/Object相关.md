

### Object.create()  : Object

     Object.create = function (o) {
       function F() {}   // 定义一个隐式的构造函数
       F.prototype = o 
       return new F()  // 本质还是通过 new 来实现
     }

 通过 Object.create() 方法，使用一个指定的原型对象和一个额外的属性对象创建一个新对象。
 这是一个用于对象创建、继承和重用的强大的新接口。说直白点，就是一个新的对象可以继承一个对象的
 属性，并且可以自行添加属性

### Object.create(null) : Object

 使用 `null` 来创建一个新的对象，`null` 是没有任何属性和方法，继承了一个null,
 所以里面没有任何东西
 
### Object.freeze(obj : Object) : Object
 
 冻结对象，不能给对象添加属性，不能更改属性值，不能删除指定的属性；
 不能修改属性的可枚举性，可配置性，可写性
 
 
     const foo = Object.freeze({});
     
     // 常规模式时，下面一行不起作用；
     // 严格模式时，该行会报错
     foo.prop = 123;
     
### Object.keys(obj : Object) : []     

> 用于返回 `Object` 对象所有可枚举的属性数组，循序和`for...in`一样 
(`for...in`还会循环原型链上)

几种用法

- 正常顺序

        var obj = { "a" : 10, "b": "dfdff" }
        
        console.log(Object.keys(obj))
        
        输出：['a','b']
    
- 其他顺序
    
       var obj = { 100: "a", 2: "b", 7: "c"}
        
       console.log(Object.keys(obj))
        
       输出： console: ["2", "7", "100"] 
   
- 函数
   
       var obj2 = Object.create({}, { getFoo : { value : function () { return this.foo } } });
       
       obj2.foo = 1;
       
       console.log(Object.keys(obj2)); 
       
       // console: ["foo"]
   
- 传入字符串，返回索引

       var str = 'ab1234';
       
       console.log(Object.keys(obj));  
       
       //[0,1,2,3,4,5]
       
- 数组 返回索引

      var arr = ["a", "b", "c"];
     
      console.log(Object.keys(arr)); 
      
      // console: ["0", "1", "2"]      
    


 
 



