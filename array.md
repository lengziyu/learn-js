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
