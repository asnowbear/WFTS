## JS 静态类型检查 (Faccbaook flow)

### 1、产生原因

-  JS 是弱类型语言(weakly languge)

-  在大规模前端构建时，代码不可控

### 2、使用方法

   JS 文件头部

   - // @flow
   
   - /* @flow */ [见vue源码]

### 3、使用场景

#### 3.1、基本类型

- boolean:

- number:

- string:

- null:

- void:


```
// @flow

let hello: string = 'hello' // 报错

hello = 2 * 2  // 报错

hello = [] // 报错

hello = 'hi' // 重新赋值
```

#### 3.2、函数

```
function plus (a: number, b: number): number {
    return a + b
}

plus()  // 报错
plus(1)  // 报错
plus('hello') // 报错
plus('hello', 'hi') // 报错
plus({}, {}) // 报错

plus(1, 2) // 3
```

#### 3.3、可能（Maybe）,可选（Optinal）,语义(Literal)，混合(Mixed)

- 可能(Maybe)类型，用一个 ? 包括类型本身，null, undefined

```
let hello: ?string // 声明一个数据类型是: string ,null ,undefined
hello = null
hello = undefined
hello = 'hello'
hello = 1  // 报错
hello = true  // 报错
```

- 可选（Optional）类型，用于对象属性，函数参数，在名称加 ? ，包含类型本身，undefined

```
const obj: {hello? : string} // 属性 hello 可以是 string, undefined
obj = {}
obj = {hello: undefined}
obj = {hello: 'hello'}
obj = {hello: null} // 报错
obj = {hello: 1}    // 报错
obj = {hello: true} // 报错

function method(param? : number) {}

method()
method(undefined)
method(1.12)
method(null)   // 报错
method('hello') // 报错
```

- 语义(Literal)类型一版用于声明某个，某几个特定的值（多值用 | 分隔）

```
let hello = 'hello'

hello = 'hello'
hello = 'hi'
hello = 12
hello = undefined
hello = null

function method(param: 1 | 'hi' | boolean): void {}

method()   // 报错，缺少参数
method(1)
method(1.2) // 报错，类型不对
method('hi') // 正确，等于特定的值
method('hello') // 报错，类型不对
method(true)
method(false)
```

- 混合（Mixed）类型，指任意数据类型

```
let hello: mixed // 声明一个 mixed 类型的变量

// 全部赋值都正确
hello = 'hello'
hello = 'hi'
hello = 12
hello = undefined
hello = null
```

### 3.4、复合类型

- 数组

```
let arr1: Array<boolean> = [true, false, true] // 声明一个元素是boolean的数组
arr1 = [true, 1] // 报错，1 不是 boolean 类型
arr1 = [''] // 报错， ‘’ 不是 boolean 类型

let arr2: Array<string> = ['A', 'B', 'C'] // 声明一个元素是 string 的数组

let arr3: Array<mixed> = [1, true, 'three'] // 声明一个任意类型的数组

arr3 = [true, 1]
arr3 = ['']
```

- map

```

// 声明一个 map 类型，其中一个名为 foo ，类型为 boolean 的子元素
 let obj1: { foo: boolean } = { foo: true }
 obj1 = {}  // 报错，缺少 foo 这个属性值
 obj1 = { foo: 1 } // 报错， 缺少这个 foo 这个属性值
 obj1 = { foo: false, bar: 'hello' } // 正确

// 声明一个 map 对象，并定义属性名称，和值类型
 let obj2: {
    foo: number,
    bar: boolean,
    baz: string
 } = {
    foo: 1,
    bar: true,
    bar: 'three'
 }

```

### 4 使用

- 安装

```
# 全局安装
npm i -g flow-bin

# 本地安装
npm i -D flow-bin
```

- 使用

```
flow init                   # 初始化项目

flow check path/to/dir      # 检查这个目录下所有的文件
flow check path/to/js/file  # 检查指定文件
```


### 5、 配合 babel 一起使用

- babel-parset-flow

    在程序运行的时候，进行静态类型检查

- babel-plugin-flow-runtime

    用于开发环境，进行数据类型的检查




