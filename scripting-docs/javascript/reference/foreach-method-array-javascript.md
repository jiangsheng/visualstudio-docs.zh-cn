---
title: "forEach 方法 (Array) (JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "数组 [JavaScript], forEach 方法"
  - "回调函数, forEach 方法 [JavaScript]"
  - "forEach 方法 [JavaScript]"
ms.assetid: bd188034-a62b-4cbd-99c8-46d70dd6823d
caps.latest.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 28
---
# forEach 方法 (Array) (JavaScript)
为数组中的每个元素执行指定操作。  
  
## 语法  
  
```  
  
array1.forEach(callbackfn[, thisArg])  
```  
  
#### 参数  
  
|参数|定义|  
|--------|--------|  
|`array1`|必选。  一个数组对象。|  
|`callbackfn`|必选。  最多可以接受三个参数的函数。  对于数组中的每个元素，`forEach` 都会调用 `callbackfn` 函数一次。|  
|`thisArg`|可选。  `callbackfn` 函数中的 `this` 关键字可引用的对象。  如果省略 `thisArg`，则 `undefined` 将用作 `this` 值。|  
  
## 异常  
 如果 `callbackfn` 参数不是函数对象，则将引发 `TypeError` 异常。  
  
## 备注  
 对于数组中出现的每个元素，`forEach` 方法都会调用 `callbackfn` 函数一次（采用升序索引顺序）。  将不会为数组中缺少的元素调用回调函数。  
  
 除了数组对象之外，`forEach` 方法可由具有 `length` 属性且具有已按数字编制索引的属性名的任何对象使用。  
  
## 回调函数语法  
 回调函数的语法如下所示：  
  
 `function callbackfn(value, index, array1)`  
  
 你可使用最多三个参数来声明回调函数。  
  
 回调函数的参数如下所示。  
  
|回调参数|定义|  
|----------|--------|  
|`value`|数组元素的值。|  
|`index`|数组元素的数字索引。|  
|`array1`|包含该元素的数组对象。|  
  
## 修改数组对象  
 `forEach` 方法不直接修改原始数组，但回调函数可能会修改它。  下表描述了在 `forEach` 方法启动后修改数组对象所获得的结果。  
  
|`forEach` 方法启动后的条件|元素是否传递给回调函数？|  
|------------------------|------------------|  
|在数组的原始长度之外添加元素。|否。|  
|添加元素以填充数组中缺少的元素。|是，如果该索引尚未传递给回调函数。|  
|元素已更改。|是，如果该元素尚未传递给回调函数。|  
|从数组中删除元素。|否，除非该元素已传递给回调函数。|  
  
## 示例  
 下面的示例阐释了 `forEach` 方法的用法。  
  
```javascript  
// Define the callback function.  
function ShowResults(value, index, ar) {  
    document.write("value: " + value);  
    document.write(" index: " + index);  
    document.write("<br />");  
}  
  
// Create an array.  
var letters = ['ab', 'cd', 'ef'];  
  
// Call the ShowResults callback function for each  
// array element.  
letters.forEach(ShowResults);  
  
// Output:  
//  value: ab index: 0   
//  value: cd index: 1   
//  value: ef index: 2   
```  
  
## 示例  
 在下面的示例中，`callbackfn` 参数包含回调函数的代码。  
  
```javascript  
// Create an array.  
var numbers = [10, 11, 12];  
  
// Call the addNumber callback function for each array element.  
var sum = 0;  
numbers.forEach(  
    function addNumber(value) { sum += value; }  
);  
  
document.write(sum);  
// Output: 33  
  
```  
  
## 示例  
 下面的示例阐释了 `thisArg` 参数的用法，该参数指定可对其引用 `this` 关键字的对象。  
  
```javascript  
// Define the object that contains the callback function.  
var obj = {  
    showResults: function(value, index) {  
        // Call calcSquare by using the this value.  
        var squared = this.calcSquare(value);  
  
        document.write("value: " + value);  
        document.write(" index: " + index);  
        document.write(" squared: " + squared);  
        document.write("<br />");  
    },  
    calcSquare: function(x) { return x * x }  
};  
  
// Define an array.  
var numbers = [5, 6];  
  
// Call the showResults callback function for each array element.  
// The obj is the this value within the   
// callback function.  
numbers.forEach(obj.showResults, obj);  
  
// Embed the callback function in the forEach statement.  
// The obj argument is the this value within the obj object.  
// The output is the same as for the previous statement.  
numbers.forEach(function(value, index) { this.showResults(value, index) }, obj);  
  
// Output:  
//  value: 5 index: 0 squared: 25  
//  value: 6 index: 1 squared: 36  
//  value: 5 index: 0 squared: 25  
//  value: 6 index: 1 squared: 36  
```  
  
## 要求  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## 请参阅  
 [filter 方法 \(Array\)](../../javascript/reference/filter-method-array-javascript.md)   
 [map 方法 \(Array\)](../../javascript/reference/map-method-array-javascript.md)   
 [some 方法 \(Array\)](../../javascript/reference/some-method-array-javascript.md)   
 [Array 对象](../../javascript/reference/array-object-javascript.md)   
 [使用数组](../../javascript/advanced/using-arrays-javascript.md)   
 [Hilo JavaScript 示例应用（Windows 应用商店）](http://hilojs.codeplex.com/SourceControl/latest)