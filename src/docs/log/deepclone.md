# deepClone 深度克隆（拷贝）

----

> 为解决数据污染，必须对一些数据做深度克隆，保证多处使用，不受干扰。

## deepclone.js

```javascript

/**
 * 对象深拷贝
 */
 const getObjType = obj => {
    var toString = Object.prototype.toString;
    var map = {
        "[object Boolean]": "boolean",
        "[object Number]": "number",
        "[object String]": "string",
        "[object Function]": "function",
        "[object Array]": "array",
        "[object Date]": "date",
        "[object RegExp]": "regExp",
        "[object Undefined]": "undefined",
        "[object Null]": "null",
        "[object Object]": "object"
    };
    if (obj instanceof Element) {
        return "element";
    }
    return map[toString.call(obj)];
};

 export const deepClone = data => {
    var type = getObjType(data);
    var obj;
    if (type === "array") {
        obj = [];
    } else if (type === "object") {
        obj = {};
    } else {
        //不再具有下一层次
        return data;
    }
    if (type === "array") {
        for (var i = 0, len = data.length; i < len; i++) {
            obj.push(deepClone(data[i]));
        }
    } else if (type === "object") {
        for (var key in data) {
            obj[key] = deepClone(data[key]);
        }
    }
    return obj;
}

```

## 使用例子

```javascript
var arr = [1, 2, 3, 5]
var cloneArr = deepClone(arr)
console.log(cloneArr)   // --> [ 1, 2, 3, 5 ]
console.log(arr === cloneArr)   // --> false

var obj = { name: 'leson', age: 18 }
var cloneObj = deepClone(obj)
console.log(cloneObj)   // --> { name: 'leson', age: 18 }
console.log(obj === cloneObj)   // false
obj.name = 'lsc'
console.log(obj)    // --> { name: 'lsc', age: 18 }
console.log(cloneObj)   // --> { name: 'leson', age: 18 }

```