# DOM操作
> 与jQuery对比

## 目录
- [Add Class](#add-class)
- [After](#after)
- [Before](#before)
- [Append](#append)
- [Children](#children)
- [Clone](#clone)
- [Contains](#contains)
- [Contains Selector](#contains-celector)
- [Each](#each)
- [Empty](#empty)
- [Filter](#filter)
- [Find Children](#find-fhildren)
- [Find Elements](#find-elements)
- [Get Attributes](#get-attributes)
- [Get HTML](#get-html)
- [Get Outer Html](#get-outer-html)
- [Get Style](#get-style)
- [Get Text](#get-text)
- [Has Class](#has-class)
- [Matches](#matches)
- [Next](#next)
- [Outer Width](#outer-width)
- [Outer Height](#outer-height)
- [Parent](#parent)
- [Position](#position)
- [Perpend](#perpend)
- [Prev](#prev)
- [Remove](#remove)
- [Remove Class](#remove-class)
- [Replace From Html](#replace-from-html)
- [Set Attributes](#set-attributes)
- [Set Html](#set-html)
- [Set Text](#set-text)
- [Set Style](#set-style)
- [Siblings](#siblings)
- [Toggle Class](#toggle-class)


Add Class
---------
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
After
-----
```
//jquery
$(el).after(htmlString);

//IE8+
el.inserAdjacentHTML('afterend', htmlString);
```

Before
------
```
//jquery
$(el).before(htmlString);

//IE8+
el.insterAdjacentHTML('beforebegin', htmlString);
```

Append
------
```
//juqery
$(parent).append(el);

//I8+
parent.appendChild(el);
```

Children
--------
```
//jquery
$(el).children();

//IE8+
el.children;
```

Clone
-----
```
//jquery
$(el).clone();

//IE8+
el.cloneNode(true);
```

Contains
--------
```
//jquery
$.contains(el, child);

//IE8+
el !== child && el.contains(child);
```


Contains Selector
-----------------
```
//jquery
$(el).find(selector).length;

//IE8+
el.querySelector !== null;
```

Each
----
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

Empty
-----
```
//jquery
$(el).empty();

//IE9+
el.innerHTML = '';
```

Filter
------
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

Find Children
-------------
```
//jquery
$(el).find(selector);

//IE8+
el.querySelectorAll(selector);
```

Find Elements
-------------
```
//jquery
$('#my .selector');

//IE8+
document.querySelectorAll('#my .selector');
```

Get Attributes
--------------
```
//jquery
$(el).attr('tabindex');

//IE8+
el.getAttributes('tabindex');
```

Get HTML
--------
```
//jquery
$(el).html();

//IE8+
el.innerHTML;
```

Get Outer Html
--------------
```
//jquery
$('div').append($(el).clone()).html();

//IE8+
el.outerHtml
```

Get Style
---------
```
//jquery
$(el).css(ruleName);

//IE9+
getComputedStyle(el)[ruleName];
```

Get Text
--------
```
//jquery
$(el).text();

//IE8+
el.textContent;
```

Has Class
---------
```
//jquery
$(el).hasClass(className);

//IE8+
if(el.classList){
 el.classList.contains(className);
}else{
 new RegExp('(^| )' + className + '( |$)', 'gi').test(el.className);
}
```

Matches
-------
```
//jquery
$(el).is($(ortherEl));

//IE8+
el === ortherEl
```

Next
----
```
//jquery
$(el).next();

//IE9+
el.nextElementSbling;
```

Outer Width
-----------
```
//jquery
$(el).outerWidth()

//IE8+
el.offsetWidth;
```

Outer Height
------------
```
//jquery
$(el).outerHeight();

//IE8+
el.offsetHeight;
```

Parent
------
```
//jquery
$(el).parent();

//IE8+
el.parentNode;
```

Position
--------
```
//jquery
$(el).position();

//IE8+
{
  left: el.offsetLeft,
  top: el.offsetTop
}
```

Perpend
-------
(在什么地方之前插件内容)
```
//jquery
$(parent).perpend(el);

//IE8+
parent.inserBefor(el, parent.firstChild);
```

Prev
----
```
//jquery
$(el).prev();

//IE9+
el.previousElementSibling
```

Remove
------
```
//jquery
$(el).remove();

//IE8+
el.parentNode.removeChild(el);
```

Remove Class
------------
```
//jquery
$(el).removeClass(className);

//IE8+
if(el.classList){
  el.classList.remove(className);
}else{
  el.className = el.className.replace(new RegExp('(^|\\b)' + className.split(' ').join('|') + '(\\b|$)', 'gi'), ' ');
}
```

Replace From Html
-----------------
(替换内容)
```
//jquery
$(el).replaceWidth(string);

//IE8+
el.outerHTML = string;
```

Set Attributes
--------------
```
//jquery
$(el).attr('value', 3);

//IE8+
el.setAttributes('value', 3);
```

Set Html
--------
```
//jquery
$(el).html(string);

//IE8+
el.innerHTML = string;
```

Set Text
--------
```
//jquery
$(el).text(string);

//IE8+
el.textContent = string;
```

Set Style
---------
```
//juqery
$(el).css('border-color', '#000000');

//IE8+
el.style.borderColor = '#000000';
```

Siblings
--------
```
//jquery
$(el).siblings();

//IE8+
Array.prototype.filter.call(el.parentNode.children, function(child) {
  return child !== el
})
```

Toggle Class
------------
```
//jquery
$(el).toggleClass(className);

//IE9+
if(el.classList){
  el.classList.toggle(className);
}else{
  var classes = el.className.split('');
  var existingIndex = classes.indexOf(className);
  if(existingIndex >= 0){
    classes.splice(existingIndex, 1);
  }else{
    classes.push(className);
  }
  el.className = classes.join('');
}
```

来自[youmightnotneedjquery](http://youmightnotneedjquery.com/#add_class)
