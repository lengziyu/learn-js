# AJAX
> 与jquery对比
- [JSON](#json)
- [POST](#post)
- [Request](#request)


JSON
----
```
// jquery
$.getJSON('/url', function(data) {

});

// IE9+
var request = new XMLHttpRequest();
request.open('GET', '/url', true);

request.onload = function() {
  if (request.status >= 200 && request.status < 400) {
    //Success
    var data = JSON.parse(request.responseText);
  }else{
    // 我们达到我们目标的服务，但它返回一个错误
  }
}

request.onerror = function(){
  //这里是连接错误的分类
}

request.send();
```

POST
----
```
// jquery
$.ajax({
  type: "POST",
  url: "/url",
  data: data
})

// IE8+
var request = XMLHttpRequest();
request.open('POST', '/url', true);
request.setRequestHeader('Content-type', 'application/x-www-form-urlencoded; charset=UTF-8');
request.send();
```


Request
-------
```
// jquery
$.ajax({
  type: 'GET',
  url: '/url',
  success: function(resq) {
    //Success
  },
  error: function(){
    // Error
  }
})

//IE9+
var request = new XMLHttpRequest();
request.open('GET', '/url', true);

request.onload = function() {
  if(request.status >= 200 && request.status < 400) {
    //success
  }else{

  }
}

request.onerror = function() {
  //error
}

request.send();
```
