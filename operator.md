1. 自定义 valueOf 方法。valueOf 方法本来是返回 [objecet] 的。
var obj = {
    valueOf: function(){return 1;}
}
obj + 2 //3

12 % 5 //2

2. 自增和自减运算符是仅有的两个有副作用的运算符。副作用是指，它会改变原始值。

3. 比如 var x = 1   ++x 只有 x 就等于 2 了。此时你再去取 x 的值，那就会返回 2 ，但前面声明 x = 1 。这就改变了原始值。

4. 自增自减运算符放在前面和后面会有一点差异。放在前面会先执行运算，再返回变量的值；放在后面则反之。


5. -(-x) //1  这是负值运算符。连用两个则等同于数值运算符。但这个括号不能少，否则会变成自减运算符。我觉得背后的规律就是，任何事物都不能存在歧义，否则就会出错。

6. 指数运算符
2**4  //16   前一个是底数，后一个是指数。
2**3**2 //512 指数运算符是右结合，而不是左结合。意思是，先进行右边指数的运算，再进行左边的运算。

7. 赋值运算符。最常见的就是 = 。
var x = 1
var y = x

8. 赋值运算符与其他运算符的结合
x += y 即 x = x+y
x -= y 即 x = x-y
x *= y 即 x = x*y
x /= y 即 x = x/y
x %= y 即 x = x%y
x **= y 即 x = x**y

9. 比较运算符：用于比较两个值的大小，然后返回一个布尔值，表示是否满足指定的条件。注意，比较运算符可以比较各种类型的值，不仅仅是数值。
JavaScript 一共提供了 8 个比较运算符。
- > 大于运算符
- < 小于运算符
- <= 小于或等于运算符
- >= 大于或等于运算符
- == 相等运算符
- === 严格相等运算符
- != 不相等运算符
- !=== 严格不相等运算符

比较运算符分成两类：相等比较 和 非相等比较。对于非相等比较，算法是先看两个运算子是否都是字符串。如果是，则比较 Unicode 码点；否则会将运算字都转成数值，再比较数值的大小。

非相等运算符之 字符串的比较：JavaScript 引擎内部先比较首字符的 Unicode 码点，如果相等，再比较第二个，以此类推。
比如： 'cat' > 'dog'

 