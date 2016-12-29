# DOM操作
> 与jQuery对比

### Add Class
```
//jquery
$(el).addClass(className);

//IE8+
var el = document.getElementById('el');
if(el.classList){
  el.classList.add(className);
}else{
  el.className += '' + className;
};
```
