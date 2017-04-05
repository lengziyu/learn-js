# 常见问题
### null和undefined的区别

null表示“没有对象”，即该处不应该有值。典型的用法是：
- 作为函数的参数，表示该函数的参数不是对象；
- 作为对象原型链的终点。
```
Object.getPrototypeOf(Object.pritotype);
// null
```
nudefined表示“缺少值”，此处应该有值的，但是没有定义。典型用法是：
- 变量被声明，但是没有赋值，此时等于undefined；
- 调用函数时，应该提供的参数没有提供，此参数等于undefined；
- 对象没有赋值的属性，该属性的值为undefined；
- 函数没有返回值时，默认返回undefined。
```
var a;
a // undefined

function f(a){
  console.log(a);
};
f(); // undefined

var a = new Object();
a.b // undefined

var x = f();
x // undefined
```
