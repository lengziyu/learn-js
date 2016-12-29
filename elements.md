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
### After
```
//jquery
$(el).after(htmlString);

//IE8+
el.inserAdjacentHTML('afterend', htmlString);
```

### Before
```
//jquery
$(el).before(htmlString);

//IE8+
el.insterAdjacentHTML('beforebegin', htmlString);
```

### Append
```
//juqery
$(parent).append(el);

//I8+
parent.appendChild(el);
```

### Children
```
//jquery
$(el).children();

//IE8+
el.children;
```

### Clone
```
//jquery
$(el).clone();

//IE8+
el.cloneNode(true);
```
