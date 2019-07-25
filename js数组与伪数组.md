1. js内存里分 stack 和 heap 两个区，stack 里存了 global/浏览器里叫window 。window 对应的是 heap 里的对象，是一个哈希表。哈希表分为标准库和非标准库。

2. 在控制台里，String(1) //"1"  如果是 new String(1)  就会变成一个 String 对象。 new Number(123) 也是一样，返回的就是一个 123 组成的对象。似乎有 new 就会返回一个对象？

3. 复习一下五个 falsy 值，Boolean() 一下，就会返回 false 的。 false 0 NaN undefined null ''/""

4. 数组的长度
```
var a = Array(3)
// 只有一个参数的时候，这个参数就是数组的长度

var b = Array(3,3)
// 有两个参数的时候，这两个就是数组的内容了，所以该数组的长度 b.length === 2

这种区别叫做「不一致性」

var a = new Array(3,3)  // 加不加 new 对 Array 来说都一样。
```

5. 如果是基本类型：字符串、数值、布尔值，加 new 的话返回的是对象；但是对于对象来说，加不加 new 是一样的。
```
Number(123)      // 这返回的是基本数据类型
new Number(123)  // 这会返回一个对象
```

6. 函数
```
一种声明函数的方法是：
var f = function(a,b){
    return a+b
}
f(3,4)

另一种声明的函数是：
var f = new Function('a','b','return a+b')
f(1,2) //这种方法没人用，知道就行了。这种方式是用全句对象在声明一个函数。

function f(){
    return x+y
}
// 这种方式声明函数必须要有 return ，可以没有参数。

三种声明函数的方式，叫具名函数，匿名函数，new Function。具名函数有名字，一步到位直接初始化出变量和函数，并把两者连接；匿名函数 var f = function(){} 这种方式其实先声明了一个变量f，然后再把变量和函数连接。第三种没人用。

```

7. 数组，由 Array 构造出来的对象就是数组。

8. js 的体积很小，功能很强大。比如一个数组，可以只有一个值，但他的 proto 连接到了共用属性，所以功能强大。

9. 数组和狭义对象的区别是，数组的 proto 指向的是数组的共用属性，而数组的共用属性的 proto 再指向终极对象的共用属性。而狭义对象的 proto 指向的是终极对象的公用属性。画个图就明白了。数组和对象都是对象，只是原型链不同。

10. 遍历对象
```
var a = [1,2,3]
a.yyy = 'yyy'
a.xxx = 'xxx'

第一种遍历方式：
for(let i=0; i<a.length; i++){
    console.log(a[i])
}

// 这样遍历不会遍历到 xxx 和 yyy 这两个 key，因为声明的 i 是数字，而且是 i++.

第二种遍历方式：
for(let key in a){
    console.log(key)
}

// 这样遍历就会遍历所有 key 了。
```

11. 伪数组：你的原型链中没有 Array.prototype 这一环，就是伪数组。js 中只有一个伪数组，就是 arguments.

12. a.forEach()  forEach API , 这是需要接收函数的 API .
```
a.forEach(function(x,y){
    console.log('value',x)  // x 是value ， key 是 y
    console.log('key',y)
})

这个函数必须接收两个（三个）参数，名字任意取。
```

13. console.log(arguments)   // arguments 就是函数接受的参数，这样可以打印出来。

14. 关于数组
```
a = ['fff', 'kkk', 'jjj'];
a.forEach(function(b,c,d){
    console.log(b,c,d)
})

a.forEach 里面一定是一个函数，函数里面一定有三个参数，第一个参数必是 value ，第二个参数必是 key ，第三个参数必是数组本身。
```

15. a.sort()  数组排序  js内置的排序一般是快排。
```
a = [1,4,2,3,5,7,8];
a.sort()  // [1, 2, 3, 4, 5, 7, 8]

a.sort( function(x,y){ return x-y } )  // 这样写一般是从小到大。决定前后顺序。

a.sort( function(x,y){ return y-x } )  // 这样写一般是从大到小排
```

