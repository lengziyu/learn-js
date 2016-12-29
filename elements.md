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

### Contains
```
//jquery
$.contains(el, child);

//IE8+
el !== child && el.contains(child);
```


### Contains Selector
```
//jquery
$(el).find(selector).length;

//IE8+
el.querySelector !== null;
```

### Each
```
//jquery
$(selector).each(function(i, el) {
  //console.log(el);
});

//IE9+
var elements = document.querySelectorAll(selector);
Array.prototype.forEach.call(elements, function(el, i) {
  //console.log(el);
});
```

### Empty
```
//jquery
$(el).empty();

//IE9+
el.innerHTML = '';
```

### Filter
```
//jquery
$(selector).filter(function() {
  //
});

//IE9+
var elements = document.querySelectorAll(selector);
Array.prototype.filter.call(elements, function() {
  //
});
```

### Find Children
```
//jquery
$(el).find(selector);

//IE8+
el.querySelectorAll(selector);
```

### Find Elements
```
//jquery
$('#my .selector');

//IE8+
document.querySelectorAll('#my .selector');
```

### Get Attributes
```
//jquery
$(el).attr('tabindex');

//IE8+
el.getAttributes('tabindex');
```
