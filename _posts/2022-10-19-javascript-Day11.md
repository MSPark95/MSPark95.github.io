---
layout: post
title: "Javascript 11일차"
description: "Javascript 11일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/19/
---
# 11일차

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Document</title>
<script
src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.1/jquery.min.js">
</script>
</head>
<body>
<script></script>
</body>
</html>

```


```javascript
$(function () {
$("#myid").css("border", "1px solid blue").css("background-color", "black");
$(".myclass").css("text-align", "center");
$("h1").css("font-size", "3px");
$(".myclass:nth-child(1)").css("font-size", "30px");
$("h1 #myid")
});
```

```javascript
<script>
$(function () {
var obj = [{ area: "서울" }, { area: "부산" }, { area: "전주" }];

$(obj).each(function (index, item) {
console.log(`${index} : ${item.area}`);
});
console.log("==== The End 1 ====");

// $("#menu1 li").each(function (index, item) {
// console.log(`${index} : ${$(this)}`);
// });

// $.each( $("#menu1 li"), function (index, item) {
// console.log(index+":"+ item);
// });

$.each( $("#menu1 li"), function (index, item) {
console.log(item.innerHTML);
});

console.log("==== The End 2 ====");
});
</script>
```





```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Document</title>
<!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.1/jquery.min.js"></script> -->
<script src="javascripts/jquery.min.js"></script>
</head>
<body>
<p id="myid"></p>
<script>
$(function () {
$("#myid").html(
"<div><img src='https://jquery.com/jquery-wp-content/themes/jquery/content/donate.png'></div>"
);

setTimeout(
function() { $("img").attr(
"src",
"https://jquery.com/jquery-wp-content/themes/jquery/content/books/jquery-in-action.jpg"
)},
5000
);
});
</script>
</body>
</html>


피테그안에 디브테그 넣고 그안에 아이엠지테그 넣고 속성에
https://jquery.com/jquery-wp-content/themes/jquery/content/donate.png 
5초후에
https://jquery.com/jquery-wp-content/themes/jquery/content/books/jquery-in-action.jpg
```


```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Document</title>
<!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.1/jquery.min.js"></script> -->
<script src="javascripts/jquery.min.js"></script>
</head>
<body>
<p id="myid"></p>
<script>
$(function () {
$("#myid").html(
"<div><img id='image' src='https://jquery.com/jquery-wp-content/themes/jquery/content/donate.png'></div>"
);
setTimeout(function () {
$("img").attr(
"src",
"https://jquery.com/jquery-wp-content/themes/jquery/content/books/jquery-in-action.jpg"
);
}, 5000);
$('#image').fadeIn(1000).delay(5000).fadeOut(1000);

});
</script>
</body>
</html>

피테그안에 디브테그 넣고 그안에 아이엠지테그 넣고 속성에
https://jquery.com/jquery-wp-content/themes/jquery/content/donate.png 5초후에
https://jquery.com/jquery-wp-content/themes/jquery/content/books/jquery-in-action.jpg
```