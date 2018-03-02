

## DocumentFragment

  - `DocumentFragment`节点不属于文档树，继承的`parentNode`属性总是`null`
 
  - 把`DocumentFragment`节点插入文档树时，插入的不是`DocumentFragment`自身，而是它的所有子孙节点。
 
  - 这个特性使得`DocumentFragment`成了占位符，暂时存放那些一次插入文档的节点。它还有利于实现文档的剪切、复制和粘贴操作。
  
  - 当需要添加多个`dom`元素时，如果先将这些元素添加到DocumentFragment中，再统一将DocumentFragment
  
    添加到页面，会减少页面渲染dom的次数，效率会明显提升