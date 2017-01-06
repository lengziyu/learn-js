# 操作数组

### 数组去重方法

**Array.prototype.indexOf()**

运用`Array.prototype.indexOf()`方法：
```
function unique(arr) {
    return arr.filter(function(item, index){
        // indexOf返回第一个索引值，
        // 如果当前索引不是第一个索引，说明是重复值
        return arr.indexOf(item) === index;
    });
}
```
```
function unique(arr) {
    var ret = [];
    arr.forEach(function(item){
        if(ret.indexOf(item) === -1){
            ret.push(item);
        }
    });
    return ret;
}
```
**Array.prototype.includes()**

`Array.prototype.includes()`是ES2016中新增的方法，用于判断数组中是否包含某个元素，所以上面使用indexOf()方法的第二个版本可以改写成如下版本：
```
function unique(arr) {
    var ret = [];
    arr.forEach(function(item){
        if(!ret.includes(item)){
            ret.push(item);
        }
    });
    return ret;
}
```
那么，你猜猜，includes()又是用什么方法来比较的呢？如果想当然的话，会觉得肯定跟indexOf()一样喽。但是，程序员的世界里最怕想当然。翻一翻规范，发现它其实是使用的另一种比较方法，叫作“SameValueZero”比较（[https://tc39.github.io/ecma262...](https://tc39.github.io/ecma262/2016/#sec-samevaluezero)）。

注意2.a，如果x和y都是NaN，则返回true！也就是includes()是可以正确判断是否包含了NaN的。我们写一段代码验证一下：
```
var arr = [1, 2, NaN];
arr.indexOf(NaN); // -1
arr.includes(NaN); // true
```
可以看到indexOf()和includes()对待NaN的行为是完全不一样的。


