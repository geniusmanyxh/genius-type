# genius-type
A library of tools for javaScript data types



[我的个人博客地址](https://www.geniusman.top/)



[CSDN文章地址](http://t.csdn.cn/GQYv8)



[GitHub源码及文档地址](https://github.com/geniusmanyxh/genius-type)



主要功能：就是可以判断较细粒度的数据类型："string" | "number" | "bigint" | "boolean" | "symbol" | "undefined" | "object" | "function" | "array" |  "object" | "date" | "null" | "int" | "float" | "infinite" | "NaN"

## 一、安装

- 1、到GitHub源码地址下载`static` 目录下的`GTypeTools.js`文件,  通过 `script` 标签引入

```javascript
// https://github.com/geniusmanyxh/genius-type
<script src="GTypeTools.js" > </script>
<script>
   	let type1 = GTypeTools.getType(2.01)
	let type2 = GTypeTools.getType(1/0)
	console.log(type1) // float
	console.log(type2) // infinite
</script>

```



- 2、提供一个在线地址供大家测试时使用，但是这个方法不建议长期使用，因为我的云服务器过期了，这个就用不了啦！

```js
<script src="https://api.geniusman.top/cdn/genius-type/GTypeTools.js" > </script>
// or GTypeTools.min.js
<script>
	let type1 = GTypeTools.getType(2.01)
	let type2 = GTypeTools.getType(1/0)
	console.log(type1) // float
	console.log(type2) // infinite
</script>

```



- 3、通过 npm 安装

```js
npm install genius-type
```

项目使用

```js
import gType from "genius-type";

let type1 = gType.getType(2.01)
let type2 = gType.getType(1/0)
console.log(type1) // float
console.log(type2) // infinite

```



------



## 二、可用函数列表（function-list）

### 1、单一功能纯函数

- 1、isString()
- 2、isNumber()
- 3、isNaN()
- 4、isInt()
- 5、isFloat()
- 6、isInfinite()
- 7、isBigint()
- 8、isBoolean()
- 9、isSymbol()
- 10、isUndefined()
- 11、isNull()
- 12、isFunction()
- 13、isObject()
- 14、isArray()
- 15、isEmptyArray()
- 16、isEmptyObject()



### 2、衍生函数

此处的衍生函数内部使用了以上单一功能纯函数，衍生出来的。

- 1、getType()
- 2、getArrayTypes()
- 3、getObjectTypes()
- 4、getArrayTypeIndexs()
- 5、getObjectTypeKeys()
- 6、getArrayTypesDetail()
- 7、getObjectTypesDetail()
- 8、matchType()
- 9、toString()



## 三、具体使用演示

### 1、单一纯函数使用

#### 1.1、isString()

简介：

```tsx
/**
 * @description 判断值类型是否是一个string (字符串)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isString(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isString('hello world!')
let type2 = gType.isString(['hello'])

console.log(type1) // true
console.log(type2) // false
```



#### 1.2、isNumber()

简介：

```tsx
/**
 * @description 判断值类型是否是一个number (数值)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isNumber(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isNumber(258)
let type2 = gType.isNumber('258')

console.log(type1) // true
console.log(type2) // false
```


#### 1.3、isNaN()

简介：

```tsx
/**
 * @description 判断值类型是否是一个NaN (Not a Number)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isNaN(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isNaN(NaN)
let type2 = gType.isNaN(['hello'])

console.log(type1) // true
console.log(type2) // false
```


#### 1.4、isInt()

简介：

```tsx
/**
 * @description 判断值类型是否是一个int (整型数)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isInt(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isInt(123)
let type2 = gType.isInt(123.00)
let type3 = gType.isInt(123.01)

console.log(type1) // true
console.log(type2) // true
console.log(type3) // false
```

#### 1.5、isFloat()

简介：

```tsx
/**
 * @description 判断值类型是否是一个float (浮点数)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isFloat(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isFloat(66.01)
let type2 = gType.isFloat(88)

console.log(type1) // true
console.log(type2) // false
```


#### 1.6、isInfinite()

简介：

```tsx
/**
 * @description 判断值类型是否是一个infinite (无穷大)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isInfinite(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isInfinite(2/3)
let type2 = gType.isInfinite(1/0)

console.log(type1) // false
console.log(type2) // true
```


#### 1.7、isBigint()

简介：

```tsx
/**
 * @description 判断值类型是否是一个bigint (大整数)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isBigInt(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isBigInt(1)
let type2 = gType.isBigInt(Bigint(2))

console.log(type1) // false
console.log(type2) // true
```


#### 1.8、isBoolean()

简介：

```tsx
/**
 * @description 判断值类型是否是一个boolean (布尔型)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isBoolean(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isBoolean(true)
let type2 = gType.isBoolean('false')

console.log(type1) // true
console.log(type2) // false
```

#### 1.9、isSymbol()

简介：

```tsx
/**
 * @description 判断值类型是否是一个symbol
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isSymbol(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isSymbol(Symbol(1))
let type2 = gType.isSymbol(['hello'])

console.log(type1) // true
console.log(type2) // false
```

#### 1.10、isUndefined()

简介：

```tsx
/**
 * @description 判断值类型是否是一个undefined
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isUndefined(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isUndefined(undefined)
let type2 = gType.isUndefined(['hello'])

console.log(type1) // true
console.log(type2) // false
```


#### 1.11、isNull()

简介：

```tsx
/**
 * @description 判断值类型是否是一个null
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isNull(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isNull(null)
let type2 = gType.isNull('null')

console.log(type1) // true
console.log(type2) // false
```

#### 1.12、isFunction()

简介：

```tsx
/**
 * @description 判断值类型是否是一个function (函数) (指：function | class | () =>{} )
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isFunction(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isFunction(() => {})
let type2 = gType.isFunction(['hello'])

console.log(type1) // true
console.log(type2) // false
```

#### 1.13、isObject()

简介：

```tsx
/**
 * @description 判断值类型是否是一个object (指:{}, 非: null | function | date | class | array | other)
* @param {any} params 传入想要判断类型的参数
* @returns 是：true  | 否：false
*/
function isObject(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isObject({a:'dd'})
let type2 = gType.isObject(['hello'])

console.log(type1) // true
console.log(type2) // false
```

#### 1.14、isArray()

简介：

```tsx
/**
 * @description 判断值类型是否是一个数组 (数组)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isArray(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isArray('hello world!')
let type2 = gType.isArray(['hello'])

console.log(type1) // false
console.log(type2) // true
```

#### 1.15、isEmptyArray()

简介：

```tsx
/**
 * @description 判断值类型是否是一个empty array (空数组)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isEmptyArray(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isEmptyArray([])
let type2 = gType.isEmptyArray(['hello'])

console.log(type1) // true
console.log(type2) // false
```

#### 1.16、isEmptyObject()

简介：

```tsx
/**
 * @description 判断值类型是否是一个empty object (空对象)
 * @param {any} params 传入想要判断类型的参数
 * @returns 是：true  | 否：false
 */
function isEmptyObject(params: any): boolean
```

使用：

```js
import gType from "genius-type";

let type1 = gType.isEmptyObject({})
let type2 = gType.isEmptyObject({a:'55'})

console.log(type1) // true
console.log(type2) // false
```


### 2、衍生函数的使用

#### 2.1、getType()

简介：

```tsx
/**
 * @description 精确匹配数据类型
 * @param {any} params 需要判断类型的参数
 * @returns "string" | "number" | "bigint" | "boolean" | "symbol" | "undefined" | "object" | "function" | "array" |  "object" | "date" | "null" | "int" | "float" | "infinite" | "NaN"
 */
function getType(params: any): "string" | "number" | "bigint" | "boolean" | "symbol" | "undefined" | "object" | "function" | "array" |  "object" | "date" | "null" | "int" | "float" | "infinite" | "NaN"
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getType({})
let type2 = gType.getType([])

console.log(type1) // object
console.log(type2) // array
```

#### 2.2、getArrayTypes()

简介：

```tsx
/**
 * @description 获取数组每个下标值的基本数据类型
 * @param {Array} arr 需要判断类型的数组
 * @returns string[] 返回字符串数组
 */
function getArrayTypes(arr: any[]): string[]
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getArrayTypes([null, undefined, 555, 'str', NaN, 1/0, ()=>{},{}])
let type2 = gType.getArrayTypes([2.01, 3n, Symbol(1), ])

console.log(type1) //  ['null', 'undefined', 'int', 'string', 'NaN', 'infinite', 'function', 'object']
console.log(type2) // ['float', 'bigint', 'symbol']
```

#### 2.3、getObjectTypes()

简介：

```tsx
/**
 * @description 获取对象的属性的基本数据类型
 * @param {Object} obj 需要判断类型的对象
 * @returns string[] 返回字符串数组
 */
function getObjectTypes(obj: object): string[]
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getObjectTypes({
        a:1,
        b:'s',
        c:2.01,
        d:1/0,
        e:NaN,
        f:undefined,
        g:{},
        h:[],
        i:1n,
        j:Symbol(1),
        k:null,
        l:new Date()
      })

console.log(type1) // ['int', 'string', 'float', 'infinite', 'NaN', 'undefined', 'object', 'array', 'bigint', 'symbol', 'null', 'date']

```

#### 2.4、getArrayTypeIndexs()

简介：

```tsx
/**
 * @description 获取对应类型的数组索引
 * @param {Array} arr 需要判断类型的数组
 * @param {returnTypeStr} dataType 需要判断的类型
 * @returns number[] 返回一个字符串数组
 */
function getArrayTypeIndexs(arr: any[], dataType: string): number[]
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getArrayTypeIndexs([null, 1, 555, 'str', NaN, 1/0, ()=>{},{}],'int')

console.log(type1) // [1, 2]
```

#### 2.5、getObjectTypeKeys()

简介：

```tsx
/**
 * @description 获取对应类型的对象属性名称(key_name)
 * @param {Object} obj 需要判断类型的对象
 * @param {returnTypeStr} dataType 需要判断的类型
 * @returns string[] 返回一个字符串数组
 */
function getObjectTypeKeys(obj: object, dataType: string): string[]
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getObjectTypeKeys({
        a:1,
        b:'s',
        c:2.01,
        d:1/0,
        e:NaN,
        f:undefined,
        g:{},
        h:[],
        i:1n,
        j:Symbol(1),
        k:null,
        l:new Date()
      }, 'null')


console.log(type1) // ['k']

```

#### 2.6、getArrayTypesDetail()

简介：

```tsx
/**
 * @description 获取或者筛选数组内的值,并返回该值的index-value-type, 如果不传dataType，默认返回所有
 * @param {Array} arr 传入你想要获取的参数类型的数组
 * @param {returnTypeStr} dataType 可选参数，传入你想要获取的参数类型
 * @returns [{index:index,value:value,type:type}...]
 */
function getArrayTypesDetail(arr: any[], dataType: string): string[]
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getArrayTypesDetail([null, 1, 555, 'str', NaN, 1/0, ()=>{},{}])
let type2 = gType.getArrayTypesDetail([null, 1, 555, 'str', NaN, 1/0, ()=>{},{}],'int')
console.log(type1) 
console.log(type2)
// --------------type1打印结果-------------------
0: {index: 0, value: null, type: 'null'}
1: {index: 1, value: 1, type: 'int'}
2: {index: 2, value: 555, type: 'int'}
3: {index: 3, value: 'str', type: 'string'}
4: {index: 4, value: NaN, type: 'NaN'}
5: {index: 5, value: Infinity, type: 'infinite'}
6: {index: 6, type: 'function', value: ƒ}
7: {index: 7, value: {}, type: 'object'}

//----------------type2打印结果--------------------
0: {index: 1, value: 1, type: 'int'}
1: {index: 2, value: 555, type: 'int'}
```

#### 2.7、getObjectTypesDetail()

简介：

```tsx
/**
 * @description 获取或者筛选对象内属性的值, 并返回该值的key-value-type, 如果不传dataType，默认返回所有
 * @param {object} obj 传入你想要获取的参数类型的对象
 * @param {returnTypeStr} dataType 可选参数，传入你想要获取的参数类型
 * @returns [{key:key,value:value,type:type}...]
*/
function getObjectTypesDetail(obj: object, dataType: string): string[]
```

使用：

```js
import gType from "genius-type";

let type1 = gType.getObjectTypesDetail({
        a:1,
        b:'s',
        c:2.01,
        d:1/0,
        e:NaN,
        f:undefined,
        g:{},
        h:[],
        i:1n,
        j:Symbol(1),
        k:null,
        l:new Date()
      })
let type2 = gType.getObjectTypesDetail({
        a:1,
        b:'s',
        c:2.01,
        d:1/0,
        e:NaN,
        f:undefined,
        g:{},
        h:[],
        i:1n,
        j:Symbol(1),
        k:null,
        l:new Date()
      }, 'null')

console.log(type1) 
console.log(type2)

// ----------type1打印结果-----
0: {key: 'a', value: 1, type: 'int'}
1: {key: 'b', value: 's', type: 'string'}
2: {key: 'c', value: 2.01, type: 'float'}
3: {key: 'd', value: Infinity, type: 'infinite'}
4: {key: 'e', value: NaN, type: 'NaN'}
5: {key: 'f', value: undefined, type: 'undefined'}
6: {key: 'g', value: {…}, type: 'object'}
7: {key: 'h', value: Array(0), type: 'array'}
8: {key: 'i', value: 1n, type: 'bigint'}
9: {key: 'j', value: Symbol(1), type: 'symbol'}
10: {key: 'k', value: null, type: 'null'}
11: {key: 'l', value: Thu Jun 30 2022 16:01:31 GMT+0800 (中国标准时间), type: 'date'}

// ----------type2打印结果---------
0: {key: 'k', value: null, type: 'null'}
```

#### 2.8、matchType()

简介：

```tsx
/**
 * @description 类型匹配通用函数
 * @param {returnTypeStr | Function} fn 可以是已经存在的工具函数名称，或者你自定义的函数
 * @param {any} data 传入想要判断类型的参数
 * @returns 返回你传入函数(fn)的返回值
 */
function matchType(fn: string | Function, data: any): any
```

使用：

```js
import gType from "genius-type";

let type1 = gType.matchType('isInt', 2.01)
let type2 = gType.matchType(gType.isArray,[])
let type3 = gType.matchType((args)=>{
    return gType.isInt(args?.a)
},{a:1})

console.log(type1) // false
console.log(type2) // true
console.log(type2) // true
```

#### 2.9、toString()

简介：

```tsx
/**
 * @description 类型转换为string (字符串)
 * @param {any} params 传入想要转换类型的参数
 * @returns string
 */
function toString(params: any): string
```

使用：

```js
import gType from "genius-type";

let type1 = gType.toString(5)
let type2 = gType.toString({a:55})
let type3 = gType.toString(new Date())
let type4 = gType.toString([4,5])

console.log(type1) // '5'
console.log(type2) // {a: '55'}
console.log(type3) // 'Thu Jun 30 2022 16:31:59 GMT+0800 (中国标准时间)'
console.log(type4) // ['4','5']
```



...后续完善中！
