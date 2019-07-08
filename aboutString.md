# 数据类型相关

1. 如果要在单引号字符串的内部，使用单引号，就必须在内部的单引号前面加上反斜杠，用来转义。双引号字符串内部使用双引号，也是如此。'Did she say \'Hello\'?'

2. 字符串可以跟数组一样，用方括号取它的字符。比如：
var s = 'manameishejianxin'
```s[0] //m
s[1] //a
```
但是，字符串跟数组的相似之处仅此而已。字符串的内容是无法变更或删除的。

3. length 属性。length 是无法改变的。
```
s = 'hello'
s.length = 5
```

4. JavaScript 引擎内部，所有字符都用 Unicode 表示，并且允许在程序内部直接使用码点表示字符。
```
var s = '\u00A9';
s // "©"
```
JavaScript 输出给用户的时候，全会转成字面形式。给用户看的当然不会是码点啦。

5. parseFloat 用于将字符串转为浮点数。顾名思义，parse float 直译就是：转为，浮点数。知道英文就行了。
- parseFloat('3.14')  //3.14
- parseFloat('3.14e-2')  //3.14  如果字符串符合科学计数法，也会相应转换，无碍。
- parseFloat('3.14dslfjalsdkj')  //3.14  如果字符串包含不能转化的部分，那就不再往后转了，返回转好的部分。前面是死路，那就不走了呗。
- parseFloat('\t\v\r12.34') //12.34  parseFloat 会自动过滤前导的空格。
- parseFloat('[]')
- parseFloat('ff2')
- parseFloat('')  以上三个例子。如果参数不是字符串，或第一个字符不能转为数字，则返回 NaN 。
- Number() 方法会把 null ''(空字符串) 转为 0 。

5. isNaN() 用来判断一个值是否为 NaN。
注意，isNaN 只对数值有效，比如，传入字符串的时候，字符串会先被转成 NaN , 再返回 true 。所以，isNaN 里的可能不是 NaN , 可能是一个字符串。
- isNan('hello') //true   相当于：isNaN(Number('hello'))
出于同样的原因，对于对象和数组，isNaN 也返回 true。但对于空数组和只有一个数值成员的数组，isNaN 返回 false ，原因是这些能被 Number 转成数值。
使用 isNaN 之前最好判断一下数据类型：
```
function myIsNaN(){
    return typeof value === 'number' && isNaN(value);
}
```

6. isFinite 表示一个值是否为正常的数值。
```
isFinite(Infinity)  //false
isFinite(-Infinity) //false
isFinite(NaN)  //false
isFinite(undefined)  //false
isFinite(null)  //true
isFinite(-1)  //true
```

7. 对象。就是一组键值对（key：value）。
- 两个键值对之间用逗号分隔。 
- 对象的所有键名都是字符串，所以键名加不加单引号都行。如果键名是数值，会被自动转成字符串。
- 如果键名不符合标识名的条件，且也不是数字，则必须加上引号，否则会报错。
- 如果一个属性的值为函数，通常把这个属性（键名）称为方法，可以像函数那样调用。
- 最后一个属性后面，加不加逗号都行。
- 大括号解释为对象，圆括号解释为表达式。

```
var obj = {
    foo: 'hello',
    bar: 'world'
};

...

var case = {
    a: 1,
    b:2,
    c: function(x){
        return 2 * x
    }
}
case.c(1)  //2   如果键值是一个函数，那么可以像调用函数一样调用它的键名（键名也叫属性 property ），这种情况下，键名也叫方法。可以传参数。
```

8. 其他
- 注意，数值键名不能使用点运算符（因为会被当成小数点），只能使用方括号运算符。
- with(){} 语句，如果区块内部有赋值操作，必须是当前对象已经存在的属性，否则会创建一个全句变量。

