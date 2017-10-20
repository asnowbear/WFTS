
# new 操作符解译

代码段

    var obj = new Base()
    
其实干了三件事情
        
    var obj = {}
    obj._proto_ = Base.prototype
    Base.call(obj)