﻿# 字符串与数组方法组合函数合集

Tags： FunctionPackage

---
## 数组首尾增减函数

**封装一个函数pop删除数组的最后一位，并且返回这个被删除的元素**
```javascript
function pop(arr){
  if(!arr.length) return;
  var ret = arr[arr.length - 1];
  arr.length--;
  return ret;
}
```

**封装一个函数push向数组的最后一位添加新的元素，并且返回添加元素之后数组的长度**
```javascript
function push(arr, ele){
  arr[arr.length] = ele;
  return arr.length;
}
```

**封装一个函数shift删除数组的第一个元素，并且返回这个被删除的元素**
```javascript
function shift(arr){
  if(!arr.length) return;
  var ret = arr[0];
  for(var i=0; i<arr.length; i++){
    arr[i] = arr[i + 1];
  }
  arr.length--;
  return ret;
}
```

**封装一个函数unshift向数组最前面添加一个元素，并且返回新数组的长度**
```javascript
function unshift(arr, ele){
  for(var i=arr.length; i>=0; i--){
    arr[i] = arr[i-1];
  }
  arr[0] = ele;
  return arr.length;
}
```
***

## 驼峰转换函数
封装一个函数，将字符串"miao-wei-ke-tang"从第二个单词开始首字母大写，然后拼成字符串miaoWeiKeTang，并返回。

```javascript
var str = `miao-wei-ke-tang`;
var arr = str.split('-');

for(var i = 1;i < arr.length;i++){
    arr[i] = arr[i][0].toUpperCase() + arr[i].substr(1)；
}

console.log(arr.join('-'));
```

## 去除空格函数

封装一个函数，将字符串"      miao  v        "实现trim功能，但不使用trim方法，去掉字符串前后空格，将返回处理后的字符串。

```javascript
var str = `      miao  v        `;

function trim(str){

    while( start < end && str[start] === ' '){
    start++;
    }
    
    while( start < end && str[end] === ' '){
    end--;
    }
    
    return str.substring(start,end + 1);
}

console.log(trim(str));
```

## 找位置函数

写一个方法，找出字符串 “abcabcabcabcabcabda” 中”ab”出现的次数和位置；

```javascript
var str =`abcabcabcabcabcabc`;

var n =0,index, x = 0;

while((index = str.indexOf('ab',n)) != -1){
    x++;
    console.log(index);
    n = index + 2;
}

console.log(`总次数是${x}`);
```

## 删除数组中特定位置元素

封装为删除特定位置元素的数组函数spliceOne(arr,index) 

```javascript
function spliceOne(arr, index){
  for(var i=index; i<arr.length; i++){
    arr[i] = arr[i+1];
  }
  arr.pop();
}

spliceOne(arr, 1)  //删除数组arr中的索引值为1的元素
console.log(arr); //返回删除后的数组['a', 'c', 'd'];（改变原来的数组）
```

## 数字补零函数
```javascript
function add0(num){
		return num < 10?'0'+num:''+num;
	}
```