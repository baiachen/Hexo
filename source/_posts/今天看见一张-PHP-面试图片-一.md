---
title: 今天看见一张 PHP 面试图片(一)
date: 2018-09-01 10:08:38
tags:
- PHP
---

> 早上看见群里有人发了张关于`PHP`面试的题目，一共**23**道题目，我也来答下题目吧。

# 1. `isset`和`array_key_exists`之间的区别？

#### array_key_exists()

`array_key_exists`会检查键值的存在。这个函数会返回`true`，只要键值存在，即使值为`null`。
``` PHP
$fruits = [
        'apple' => 'red',
    'banana' => 'yellow',
    'orange' => null
];
array_key_exists("apple", $fruits);       // true 
array_key_exists("banana", $fruits);      // true 
array_key_exists("orange", $fruits);      // true
```
8 行
``` PHP
array_key_exists("orange", $fruits);      // true
```
使用`array_key_exists("orange", $fruits)`返回值为`true`

#### isset()

`isset`和`array_key_exists`不同，`isset`会同时检查键和值，只有当健存在，对应的变量不为`null`的时候才会返回`true`。
``` PHP
$fruits = [
    'apple' => 'red',
    'banana' => 'yellow',
    'orange' => null
];
isset($fruits["apple"]);      // true 
isset($fruits["banana"]);     // true 
isset($fruits["orange"]);     // false
```

8 行
``` PHP
isset($fruits["orange"]);     // false
```
使用`isset($fruits["orange"])`返回值为`false`

## 总结：
基本的区别是`isset`可用于数组和变量，`array_key_exists`只能用于数组，但是最主要的区别在于在设定的条件下的返回值，该用哪个取决于应用程序的需求。


