---
layout: post
title: "Javascript 9일차"
description: "Javascript 9일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/17/
---
# 9일차

## Javascript로 css 수정하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS속성 접근하여 색바꾸기</title>
</head>
<body>
  <p id="myid" class="bluetext">css속성접근하여 색바꾸기</p>
  <p id="myid" class="bluetext">css속성접근하여 색바꾸기</p>
  <p id="myid" class="bluetext">css속성접근하여 색바꾸기</p>

  <script>
    function changeColor(){
      documnet.getElemnetById("myid").style.color="red";
    }
    
    function changeText(){
      documnet.getElemnetByClassName("myclass").style.color="blue";
    }

    document.getElementById("myId").addEventListener("click",changeColor);
    document.getElementsByClassName("myclass")[0].addEventListener("mouseover",changeText);

  </script>
</body>
</html>
```
이때 document.getElementsByClassName("myclass")[0].addEventListener("mouseover",changeText);
에서 [0]과 같이 위치를 지정해 준 이유는 여러개의 myclass중에서 어떠한 위치에 있는 글자를 바꿀건지 설정해줘야 하기 때문이다.


## 619P 도형의 테두리와 색깔바꾸기
```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta http-equiv="X-UA-Compatible" content="ie=edge" />
<title>DOM</title>
<link rel="stylesheet" href="stylesheets/product.css" />
</head>
<body>
<!-- <p id="myid" class="bluetext">css속성접근하여 색바꾸기.</p> -->
<!-- <p class="myclass">동시에 바뀜</p> -->
<p id="myid" class="myclass">동시에 바뀜</p>
<p id="myid2" class="myclass">동시에 바뀜</p>

<script>
function changeColor() {
document.getElementById("myid").style.color = "blue";
}

document.getElementById("myid").addEventListener("click", changeColor);

document.getElementsById("myid")[0].addEventListener("click", changeColor);

document.getElementByClassName("myclass").addEventListener("click", changeColor);

document.getElementsByClassName("myclass")[1].addEventListener("click", changeColor);

</script>
</body>
</html>
```

## 라이트박스효과만들기(620P)
```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
    <title>라이트박스</title>
    <link rel="stylesheet" href="css/lightbox.css">
  </head>
  <body>
    <div class="row">
      <ul>
        <li><img src="images/tree-1-thumb.jpg" data-src="images/tree-1.jpg" class="pic"></li>
        <li><img src="images/tree-2-thumb.jpg" data-src="images/tree-2.jpg" class="pic"></li>
        <li><img src="images/tree-3-thumb.jpg" data-src="images/tree-3.jpg" class="pic"></li> 
        <li><img src="images/tree-4-thumb.jpg" data-src="images/tree-4.jpg" class="pic"></li>
        <li><img src="images/tree-5-thumb.jpg" data-src="images/tree-5.jpg" class="pic"></li>
        <li><img src="images/tree-6-thumb.jpg" data-src="images/tree-6.jpg" class="pic"></li>          
      </ul>    
    </div>

    <div id="lightbox">
			<img src="images/tree-1.jpg" alt="" id="lightboxImage">			
    </div>

    <script>
      var pics = document.getElementsByClassName("pic"); // .pic인 요소들을 가져와 pics 라는 변수에 저장. querySelectorAll(".pic")도 가능
      var lightbox = document.getElementById("lightbox");  // 라이트 박스. querySelector("#lightbox")도 가능
      var lightboxImage = document.getElementById("lightboxImage");  // 라이트 박스 안의 이미지. querySelector("#lightboxImage")도 가능

      for (i=0; i<pics.length; i++) {
        pics[i].addEventListener("click", showLightbox);
      }

      function showLightbox() {
				var bigLocation = this.getAttribute("data-src"); // bigLocation = this.data-src; 도 가능.
				lightboxImage.setAttribute("src", bigLocation);  // lightboxImage.src = bigLocation; 도 가능.
				lightbox.style.display = "block";  // 라이트박스 이미지를 화면에 표시
      }
      
      lightbox.onclick = function() {  //click 이벤트가 발생했을 때 실행할 함수 선언
				lightbox.style.display = "none";  // lightbox 요소를 화면에서 감춤
      }
    </script>
  </body>
</html>
```

```css
.row {
  width:420px;
  margin:0 auto;
}      
.row ul {
  list-style:none;
  margin:0;
  padding:0;
}
.row ul li {
  display:inline-table;        
}

/* 라이트 박스 스타일 */
#lightbox {
  position: fixed;  /* 위치 고정 */
  width:100%;  /* 너비 */
  height:100%;  /* 높이 */
  background-color:rgba(0,0,0,0.7);  /* 배경색 */
  top:0;  /* 시작 위치 - 위쪽 끝 */
  left:0; /* 시작 위치 - 왼쪽 끝 */
  display:none;  /* 화면에서 감추기 */
}

/* 라이트 박스 안의 이미지 */
#lightbox img {
  position:absolute;  /* top, left에 의해 위치 지정 */
  top:50%;  /* 위쪽에서 50% 부터 */
  left:50%;  /* 왼쪽에서 50% 부터 */
  transform:translate(-50%, -50%);  /* 요소를 화면 중앙에 표시하기 위해 이동 */
  border:5px solid #eee; /* 이미지 테두리 */       
}
```


### LightBox+추가기능
```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width" />
<title>라이트박스</title>
<link rel="stylesheet" href="stylesheets/lightbox.css" />
<link
rel="stylesheet"
href="https://unpkg.com/swiper@8/swiper-bundle.min.css"
/>

<script src="https://unpkg.com/swiper@8/swiper-bundle.min.js"></script>
</head>
<body>
<div class="row">
<ul>
<li>
<img
src="images/tree-1-thumb.jpg"
data-src="images/tree-1.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-2-thumb.jpg"
data-src="images/tree-2.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-3-thumb.jpg"
data-src="images/tree-3.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-4-thumb.jpg"
data-src="images/tree-4.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-5-thumb.jpg"
data-src="images/tree-5.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-6-thumb.jpg"
data-src="images/tree-6.jpg"
class="pic"
/>
</li>
</ul>
</div>

<div id="lightbox">
<img src="images/tree-1.jpg" alt="" id="lightboxImage" />
</div>

<div class="swiper mySwiper">
<div class="swiper-wrapper">
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/1824273/pexels-photo-1824273.jpeg?cs=srgb&dl=pexels-victor-miyata-1824273.jpg&fm=jpg" width="220px"
class="swiper-lazy"
/>
</div>
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/3219549/pexels-photo-3219549.jpeg?cs=srgb&dl=pexels-engin-akyurt-3219549.jpg&fm=jpg" width="220px"
class="swiper-lazy"
/>
</div>
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/1579240/pexels-photo-1579240.jpeg?cs=srgb&dl=pexels-stas-knop-1579240.jpg&fm=jpg" width="220px"
class="swiper-lazy"
/>
</div>
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/51415/pexels-photo-51415.jpeg?cs=srgb&dl=pexels-max-deroin-51415.jpg&fm=jpg" width="220px"
class="swiper-lazy"
/>
</div>
</div>

<div class="swiper-button-next"></div>
<div class="swiper-button-prev"></div>
<div class="swiper-pagination"></div>
</div>

<script>
var pics = document.getElementsByClassName("pic"); // .pic인 요소들을 가져와 pics 라는 변수에 저장. querySelectorAll(".pic")도 가능

var lightbox = document.getElementById("lightbox"); // 라이트 박스. querySelector("#lightbox")도 가능

var lightboxImage = document.getElementById("lightboxImage"); // 라이트 박스 안의 이미지. querySelector("#lightboxImage")도 가능

for (i = 0; i < pics.length; i++) {
pics[i].addEventListener("click", showLightbox);
}

function showLightbox() {

var bigLocation = this.getAttribute("data-src"); // bigLocation = this.data-src; 도 가능.
lightboxImage.setAttribute("src", bigLocation); // lightboxImage.src = bigLocation; 도 가능.
lightbox.style.display = "block"; // 라이트박스 이미지를 화면에 표시
}



lightbox.onclick = function () {
//click 이벤트가 발생했을 때 실행할 함수 선언
lightbox.style.display = "none"; // lightbox 요소를 화면에서 감춤
};

let swiper = new Swiper(".mySwiper", {
lazy: true,
pagination: {
el: ".swiper-pagination",
clickable: true,
},
navigation: {
nextEl: ".swiper-button-next",
prevEl: ".swiper-button-prev",
},
});
</script>
</body>
</html>
```

강사님이 블로그에서 추가한 코드

https://m.blog.naver.com/mathesis_time/221807095356
```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width" />
<title>라이트박스</title>
<link rel="stylesheet" href="stylesheets/lightbox.css" />

<link
rel="stylesheet"
href="https://unpkg.com/swiper@8/swiper-bundle.min.css"
/>

<script src="https://unpkg.com/swiper@8/swiper-bundle.min.js"></script>
</head>
<body>
<!-- <div class="row">
<ul>
<li>
<img
src="images/tree-1-thumb.jpg"
data-src="images/tree-1.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-2-thumb.jpg"
data-src="images/tree-2.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-3-thumb.jpg"
data-src="images/tree-3.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-4-thumb.jpg"
data-src="images/tree-4.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-5-thumb.jpg"
data-src="images/tree-5.jpg"
class="pic"
/>
</li>
<li>
<img
src="images/tree-6-thumb.jpg"
data-src="images/tree-6.jpg"
class="pic"
/>
</li>
</ul>
</div> -->

<!-- <div id="lightbox">
<img src="images/tree-1.jpg" alt="" id="lightboxImage" />
</div> -->

<div class="swiper mySwiper">
<div class="swiper-wrapper">
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/1824273/pexels-photo-1824273.jpeg?cs=srgb&dl=pexels-victor-miyata-1824273.jpg&fm=jpg"
width="600px"
class="swiper-lazy"
/>
</div>
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/3219549/pexels-photo-3219549.jpeg?cs=srgb&dl=pexels-engin-akyurt-3219549.jpg&fm=jpg"
width="600px"
class="swiper-lazy"
/>
</div>
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/1579240/pexels-photo-1579240.jpeg?cs=srgb&dl=pexels-stas-knop-1579240.jpg&fm=jpg"
width="600px"
class="swiper-lazy"
/>
</div>
<div class="swiper-slide">
<img
data-src="https://images.pexels.com/photos/51415/pexels-photo-51415.jpeg?cs=srgb&dl=pexels-max-deroin-51415.jpg&fm=jpg"
width="600px"
class="swiper-lazy"
/>
</div>
</div>

<div class="swiper-button-next"></div>
<div class="swiper-button-prev"></div>
<div class="swiper-pagination"></div>
</div>

<script>
var pics = document.getElementsByClassName("pic"); // .pic인 요소들을 가져와 pics 라는 변수에 저장. querySelectorAll(".pic")도 가능

var lightbox = document.getElementById("lightbox"); // 라이트 박스. querySelector("#lightbox")도 가능

var lightboxImage = document.getElementById("lightboxImage"); // 라이트 박스 안의 이미지. querySelector("#lightboxImage")도 가능

for (i = 0; i < pics.length; i++) {
pics[i].addEventListener("click", showLightbox);
}

function showLightbox() {
var bigLocation = this.getAttribute("data-src"); // bigLocation = this.data-src; 도 가능.
lightboxImage.setAttribute("src", bigLocation); // lightboxImage.src = bigLocation; 도 가능.
lightbox.style.display = "block"; // 라이트박스 이미지를 화면에 표시
}

lightbox.onclick = function () {
//click 이벤트가 발생했을 때 실행할 함수 선언
lightbox.style.display = "none"; // lightbox 요소를 화면에서 감춤
};
</script>

<script>
let swiper = new Swiper(".mySwiper", {
lazy: true,
pagination: {
el: ".swiper-pagination",
clickable: true,
},
navigation: {
nextEl: ".swiper-button-next",
prevEl: ".swiper-button-prev",
},
autoplay: {
delay: 5000,
},
});
</script>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Web Programming</title>
<link rel="stylesheet" href="stylesheets/nodelist.css" />
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
<div id="container">
<h1>Web Programming</h1>
<p>공부할 주제를 기록해 보세요</p>

<div class="container">
<form>
<div class="mb-3">
<label for="subject" class="form-label">과목명입력</label>
<input
type="text"
class="form-control"
id="subject"
aria-describedby="subject"
/>
</div>

<div>
<button
type="button"
class="btn btn-primary"
onclick="newRegister(); return false;"
>
추가
</button>
</div>
</form>
</div>
<hr />
<ol id="itemList"></ol>
</div>

<script>
function newRegister() {
var newItem = document.createElement("li"); // 요소 노드 추가
var subject = document.querySelector("#subject"); // 폼의 텍스트 필드
var newText = document.createTextNode(subject.value); // 텍스트 필드의 값을 텍스트 노드로 만들기
newItem.appendChild(newText); // 텍스트 노드를 요소 노드의 자식 노드로 추가

var itemList = document.querySelector("#itemList"); // 웹 문서에서 부모 노드 가져오기
itemList.appendChild(newItem); // 새로 만든 요소 노드를 부모 노드에 추가

subject.value = "";
}
</script>
<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
crossorigin="anonymous"
></script>
</body>
</html>
```




### node 삭제

```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Web Programming</title>
<link rel="stylesheet" href="stylesheets/nodelist.css">
</head>
<body>
<div id="container">
<h1>Web Programming</h1>
<p>공부할 주제를 기록해 보세요</p>
<p>공부가 끝난 것은 클릭해서 삭제할 수 있습니다.</p>
<form action="">
<input type="text" id="subject" autofocus>
<button onclick="newRegister(); return false;">추가</button>
</form>
<hr>
<ul id="itemList"> </ul>
</div>

<script>
function newRegister() {
var newItem = document.createElement("li"); // 요소 노드 추가
var subject = document.querySelector("#subject"); // 폼의 텍스트 필드
var newText = document.createTextNode(subject.value); // 텍스트 필드의 값을 텍스트 노드로 만들기
newItem.appendChild(newText); // 텍스트 노드를 요소 노드의 자식 노드로 추가

var itemList = document.querySelector("#itemList"); // 웹 문서에서 부모 노드 가져오기
itemList.insertBefore(newItem, itemList.childNodes[0]); // 자식 노드중 첫번째 노드 앞에 추가

subject.value="";

var items = document.querySelectorAll("li"); // 모든 항목 가져오기

for(i=0; i<items.length; i++) {
items[i].addEventListener("click",

function() { // 항목 클릭했을 때 실행할 함수
if(this.parentNode) // 부모 노드가 있다면
this.parentNode.removeChild(this); // 부모 노드에서 삭제
}

);
}

}
</script>
</body>
</html>
```

## 17장 마무리 예제
### 1번
```html

```

강사님 코드
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Document</title>
<style>
ul {
list-style: none;
}
</style>
</head>
<body>
<h3>할일 목록</h3>
<ul>
<li class="asdf">&#10003; 할일1</li>
<li class="asdf">&#10003; 할일2</li>
<li class="asdf">&#10003; 할일3</li>
<li class="asdf">&#10003; 할일4</li>
<li class="asdf">&#10003; 할일5</li>
</ul>
</body>

<script>
let items = document.querySelectorAll(".asdf");
console.log(items);

function deleteItem() {

this.style.textdecoration="line-through";
this.style.color="#ccc";
//style="text-decoration:line-through;color:#ccc;"

}

for (let i=0; i<items.length; i++) {
items[i].addEventListener("click", deleteItem)
}
</script>
</html>
```

### 2번
```html

```


책에 나와있는 코드 

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>연습문제 2</title>
  <style>
    form {
      margin-bottom:30px;
    }
    input[type="text"] {
      width:30px;
      height:20px;
      text-align: center;
    }
    button {
      margin-left:10px;
    }
    table {
      width:300px;      
    }
    table, td {
      border:1px solid #ccc;
      border-collapse: collapse;
    }
    td {
      padding:10px;
    }
  </style>
</head>
<body>
  <form>
    <input type="text" id="rCount" value="1">행 
    <input type="text" id="cCount" value="1">열    
    <button onclick="drawTable(); return false;">작성</button>
  </form>
  <div id="contents"></div>

  <script>
    function drawTable() {
      var rCount = document.querySelector("#rCount").value;
      var cCount = document.querySelector("#cCount").value;

      var newTable = document.createElement("table");
      for(i = 0; i < rCount; i++) {
        var newRow = document.createElement("tr");
        for(j = 0; j < cCount; j++) {
          var newCell = document.createElement("td");
          var cellText = document.createTextNode(i + ", " + j);
          newCell.appendChild(cellText);
          newRow.appendChild(newCell);
        }
        newTable.appendChild(newRow);   
      }
      var contents = document.querySelector("#contents");
      contents.appendChild(newTable);
    }
  </script>
</body>
</html>
```


## JS style Object





## 강사님이 추천해주시는 사이트
Thema Site<br> 
https://themewagon.com/


파이썬 Black<br>
https://www.daleseo.com/python-black/
