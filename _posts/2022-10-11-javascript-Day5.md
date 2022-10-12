---
layout: post
title: "Javascript 5일차"
description: "Javascript 5일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/11/
---
 # 5일차

```javascript
<script>
  var i;
  var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?","100"));
  var count=0;

  if (userNumber !==null){
    for (i=0;1<userNumber;i++){
      if (i % 3 === 0){
        count++;
        document.write(i+',');
        document.write("<br>");
        document.write("\\n");
      }
    }
    document.write('<p>${userNumber}까지 3의 배수의 갯수 : ${count}</p>');
  }
</script>
```

## 테이블로만들기
```javascript
document.write('</tbody></table><p></p></div>');
<script>
  var i;
  var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
  var count = 0;

  if (userNumber !== null) {
    document.write('<div class="container"><table class="table"><thead><tr><th scope="col">#</th><th scope="col">3의 배수</th></tr></thead><tbody>');
    for (i = 0; i < userNumber; i++) {
    if (i % 3 === 0) {
    count++;
    // document.write(i);
    // document.write("<br>");
    document.write('<tr><th scope="row">i</th><td>i</td></tr>');
    }
  }
    // document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
    document.write('</tbody></table><p></p></div>');
    document.write(
    `<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
    );
  }
  </script>
  <script>
    var i;
    var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
    var count = 0;

    if (userNumber !== null) {
    document.write('<div class="container"><table class="table"><thead><tr><th scope="col">#</th><th scope="col">3의 배수</th></tr></thead><tbody>');
     for (i = 0; i < userNumber; i++) {
      if (i % 3 === 0) {
     count++;
      // document.write(i);
     // document.write("<br>");
     document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
     }
   }
   // document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
    document.write('</tbody></table><p></p></div>');
    document.write(
     `<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
  );
}
</script>
```

```javascript
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
```

### 전체코드
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>

<script>
  var i;
  var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
  var count = 0;

  if (userNumber !== null) {
    document.write('<div class="container"><table class="table"><thead><tr><th scope="col">연번</th><th scope="col">3의 배수</th></tr></thead><tbody>');
    for (i = 0; i < userNumber; i++) {
    if (i % 3 === 0) {
    count++;
    // document.write(i);
    // document.write("<br>");
    document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
    }
  }
    // document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
    document.write('</tbody></table><p></p></div>');
    document.write(`<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
    );
}
</script>

    <!-- <script>
    var session = prompt("관심 언어를 선택해 주세요. 파이썬, 자바스크립트, 자바");

    switch (session) {
    case "파이썬" : document.write("<p>파이썬 세션은 <strong>201호</strong>에서 진행됩니다.</p>")
    break;
    case "자바스크립트" : document.write("<p>자바스크립트 세션은 <strong>203호</strong>에서 진행됩니다.</p>");
    break;
    case "자바" : document.write("<p>자바 세션은 <strong>205호</strong>에서 진행됩니다.</p>")
    break;
    default: alert("잘못 입력했습니다.");
    location.reload();
    }
    </> -->

  <script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
  integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
  crossorigin="anonymous"
  ></script>
</body>
</html>
```

## 배열
``` javascript
<script>
 var i;
 var sum=0;

 const array=[];
 for(i=1;i<1001;i++){
  array.push(i);
 }
 console.log(array);

 const 누적합 = array.map(function(i){
  return this.누적합+=i;
 }{누적합:0});
 console.log(누적합);

</script>
```

## OR문
```javascript
<script>
 var userNumber
</script>
```

## IF문


## 구구단

## 팩토리얼

## 나이계산하기
```javascript
<script>
 const currentDate=new Date();
 var currentYear=2022;
 var virthYear;
 var age;

 birthYear = prompt("태어난 연도를 입력하세요.(YYYY)","");
 age=currentYear-birthYear+1;
 document.write(currentYear+"년 현재<br>");
 document.write(birthYear+"년에 태어난 사람의 나이는"+age+"세입니다<br>");
 document.write(birthYear+"년에 태어난 사람의 나이는"+age+"세입니다<br>");
 fuction 만나이계산(){
  return 
 }
 계산된만나이=만나이계산("y,m,d")
 document.write('만나이는 ${계산된만나이}세 이빈다.<br>')
</script>

<script>
  function gettingOriginalAge(birth){
    const today = new Date(); //현재 날짜
    let age = today.getFullYear() - Number(birth.slice(0, 4));
    let mon = (today.getMonth()+1) - Number(birth.slice(5, 7)); //getMonth()는 0-11로 출력되므로 +1
    if (mon < 0 || (mon === 0 && today.getDate() < Number(birth.slice(8, 10)))) {
    return age = age - 1; //생일이 안지났을 경우 1을 빼줍니다.
    } else {
      return age;
    }
  }
</script>

```

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
<script>
//현년도를 가져와서
//만나이
var birth = prompt("생년월일을 입력하세요", "1980-07-15");

function gettingOriginalAge(birth) {
const today = new Date(); //현재 날짜[:5]
let age = today.getFullYear() - Number(birth.slice(0, 4));
//2022-1980 = 43
alert(age);
let mon = today.getMonth() + 1 - Number(birth.slice(5, 7)); //getMonth()는 0-11로 출력되므로 +1
//10-7 =3
//생일이 지났고
if (
mon < 0 ||
(mon === 0 && today.getDate() < Number(birth.slice(8, 10)))
) {
return (age = age - 1); //생일이 안지났을 경우 1을 빼줍니다.
} else {
return age;
}
}

const currentDate = new Date();
var currentYear = currentDate.getFullYear();
// alert(currentYear);
var birthYear;
var age;

birthYear = prompt("태어난 연도를 입력하세요. (YYYY)", "");
age = currentYear - birthYear + 1;
document.write(currentYear + "년 현재<br>");
document.write(
birthYear + "년에 태어난 사람의 나이는 " + age + "세입니다.<br>"
);
function 만나이계산() {
return;
}
계산된만나이 = gettingOriginalAge(birth);
document.write(`만나이는 ${계산된만나이} 세입니다.<br>`);
</script>

<script>
/*
var i;
var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
var count = 0;

if (userNumber !== null) {
document.write(
'<div class="container"><table class="table"><thead><tr><th scope="col">연번</th><th scope="col">3의 배수</th></tr></thead><tbody>'
);
for (i = 0; i < userNumber; i++) {
if (i % 3 === 0) {
count++;
// document.write(i);
// document.write("<br>");
document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
}
}
// document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
document.write("</tbody></table><p></p></div>");
document.write(
`<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
);
}
*/
</script>

<!-- <script>
var session = prompt("관심 언어를 선택해 주세요. 파이썬, 자바스크립트, 자바");

switch (session) {
case "파이썬" : document.write("<p>파이썬 세션은 <strong>201호</strong>에서 진행됩니다.</p>")
break;
case "자바스크립트" : document.write("<p>자바스크립트 세션은 <strong>203호</strong>에서 진행됩니다.</p>");
break;
case "자바" : document.write("<p>자바 세션은 <strong>205호</strong>에서 진행됩니다.</p>")
break;
default: alert("잘못 입력했습니다.");
location.reload();
}
</> -->

<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
crossorigin="anonymous"
></script>
</body>
</html>
```

# 원시값의 메서드

## 어퍼케이스
## 투픽스


## MATH함수

### 특수문자
특수문자는 이스케이프문자라고 불리며 역슬래시로 시작한다




#### index2.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
<script>

["Bilbo", "Gandalf", "Nazgul"].forEach((item, index, array) => {
alert(`${item} is at index ${index} in ${array}`);
});

/*let asdf = ["Bilbo", "Gandalf", "Nazgul"];

let func = function(item, index, array) {
alert(`${item} is at index ${index} in ${array}`);
}
asdf.forEach(func(item, index, array));
*/
//현년도를 가져와서
//만나이
var birth = prompt("생년월일을 입력하세요", "1980-07-15");

function gettingOriginalAge(birth) {
const today = new Date(); //현재 날짜[:5]
let age = today.getFullYear() - Number(birth.slice(0, 4)) + 1;
//2022-1980 + 1 = 43
alert(age);
alert(Number(birth.slice(0, 4)));

let mon = today.getMonth() + 1 - Number(birth.slice(5, 7)); //getMonth()는 0-11로 출력되므로 +1
//10-7 =3
//생일이 지났고
if (
mon < 0 ||
(mon === 0 && today.getDate() < Number(birth.slice(8, 10)))
) {
return (age = age - 1); //생일이 안지났을 경우 1을 빼줍니다.
} else {
return age;
}
}

const currentDate = new Date();
var currentYear = currentDate.getFullYear();
// alert(currentYear);
var birthYear;
var age;

birthYear = prompt("태어난 연도를 입력하세요. (YYYY)", "");
age = currentYear - birthYear + 1;
document.write(currentYear + "년 현재<br>");
document.write(
birthYear + "년에 태어난 사람의 나이는 " + age + "세입니다.<br>"
);
function 만나이계산() {
return;
}
계산된만나이 = gettingOriginalAge(birth);
document.write(`만나이는 ${계산된만나이} 세입니다.<br>`);
</script>

<script>
/*
var i;
var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
var count = 0;

if (userNumber !== null) {
document.write(
'<div class="container"><table class="table"><thead><tr><th scope="col">연번</th><th scope="col">3의 배수</th></tr></thead><tbody>'
);
for (i = 0; i < userNumber; i++) {
if (i % 3 === 0) {
count++;
// document.write(i);
// document.write("<br>");
document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
}
}
// document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
document.write("</tbody></table><p></p></div>");
document.write(
`<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
);
}
*/
</script>

<!-- <script>
var session = prompt("관심 언어를 선택해 주세요. 파이썬, 자바스크립트, 자바");

switch (session) {
case "파이썬" : document.write("<p>파이썬 세션은 <strong>201호</strong>에서 진행됩니다.</p>")
break;
case "자바스크립트" : document.write("<p>자바스크립트 세션은 <strong>203호</strong>에서 진행됩니다.</p>");
break;
case "자바" : document.write("<p>자바 세션은 <strong>205호</strong>에서 진행됩니다.</p>")
break;
default: alert("잘못 입력했습니다.");
location.reload();
}
</> -->

<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
crossorigin="anonymous"
></script>
</body>
</html>
```





``` html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
<script>
let obj = {
key1: "value1",
key2: "value2",
key3: "value3",
key4: "value4",
key5: "value5",
key6: "value6",
key7: "value7",
key8: "value8",
};

let objKeys = Object.keys(obj);
console.log(objKeys);

let objValues = Object.values(obj);
console.log(objValues);

let objMap = Object.keys(obj).forEach(function(key, index) {
obj[key] += "입니다";
});

console.log(objMap);

// => { 'a': 2, 'b': 4, 'c': 6 }
let objJSON = JSON.stringify(obj);
console.log(objJSON);


/*
let users = [
{ id: 1, name: "John" },
{ id: 1, name: "Pete" },
{ id: 1, name: "Mary" },
];

let user = users.filter((item) => item.id == 1);
alert(user[1].name); // Joh

["Bilbo", "Gandalf", "Nazgul"].forEach((item, index, array) => {
alert(`${item} is at index ${index} in ${array}`);
});

let asdf = ["Bilbo", "Gandalf", "Nazgul"];

asdf.forEach(function (item, index, array) {
alert(`${item} is at index ${index} in ${array}`);
});

//현년도를 가져와서
//만나이
var birth = prompt("생년월일을 입력하세요", "1980-07-15");

function gettingOriginalAge(birth) {
const today = new Date(); //현재 날짜[:5]
let age = today.getFullYear() - Number(birth.slice(0, 4)) + 1;
//2022-1980 + 1 = 43
alert(age);
alert(Number(birth.slice(0, 4)));

let mon = today.getMonth() + 1 - Number(birth.slice(5, 7)); //getMonth()는 0-11로 출력되므로 +1
//10-7 =3
//생일이 지났고
if (
mon < 0 ||
(mon === 0 && today.getDate() < Number(birth.slice(8, 10)))
) {
return (age = age - 1); //생일이 안지났을 경우 1을 빼줍니다.
} else {
return age;
}
}

const currentDate = new Date();
var currentYear = currentDate.getFullYear();
// alert(currentYear);
var birthYear;
var age;

birthYear = prompt("태어난 연도를 입력하세요. (YYYY)", "");
age = currentYear - birthYear + 1;
document.write(currentYear + "년 현재<br>");
document.write(
birthYear + "년에 태어난 사람의 나이는 " + age + "세입니다.<br>"
);
function 만나이계산() {
return;
}
계산된만나이 = gettingOriginalAge(birth);
document.write(`만나이는 ${계산된만나이} 세입니다.<br>`);
*/
</script>

<script>
/*
var i;
var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
var count = 0;

if (userNumber !== null) {
document.write(
'<div class="container"><table class="table"><thead><tr><th scope="col">연번</th><th scope="col">3의 배수</th></tr></thead><tbody>'
);
for (i = 0; i < userNumber; i++) {
if (i % 3 === 0) {
count++;
// document.write(i);
// document.write("<br>");
document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
}
}
// document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
document.write("</tbody></table><p></p></div>");
document.write(
`<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
);
}
*/
</script>

<!-- <script>
var session = prompt("관심 언어를 선택해 주세요. 파이썬, 자바스크립트, 자바");

switch (session) {
case "파이썬" : document.write("<p>파이썬 세션은 <strong>201호</strong>에서 진행됩니다.</p>")
break;
case "자바스크립트" : document.write("<p>자바스크립트 세션은 <strong>203호</strong>에서 진행됩니다.</p>");
break;
case "자바" : document.write("<p>자바 세션은 <strong>205호</strong>에서 진행됩니다.</p>")
break;
default: alert("잘못 입력했습니다.");
location.reload();
}
</> -->

<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
crossorigin="anonymous"
></script>
</body>
</html>
```


```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
<script>
let obj = {
key1: "value1",
key2: "value2",
key3: "value3",
key4: "value4",
key5: "value5",
key6: "value6",
key7: "value7",
key8: "value8",
};

let objKeys = Object.keys(obj);
console.log(objKeys);

let objValues = Object.values(obj);
console.log(objValues);

Object.keys(obj).forEach(function (key, index) {
obj[key] += "입니다";
});
console.log(obj);

for (var key in obj) {
if (obj.hasOwnProperty(key)) {
obj[key] += "입니까?";
}
}
console.log(obj);




// => { 'a': 2, 'b': 4, 'c': 6 }
let objJSON = JSON.stringify(obj);
console.log(objJSON);

/*
let users = [
{ id: 1, name: "John" },
{ id: 1, name: "Pete" },
{ id: 1, name: "Mary" },
];

let user = users.filter((item) => item.id == 1);
alert(user[1].name); // Joh

["Bilbo", "Gandalf", "Nazgul"].forEach((item, index, array) => {
alert(`${item} is at index ${index} in ${array}`);
});

let asdf = ["Bilbo", "Gandalf", "Nazgul"];

asdf.forEach(function (item, index, array) {
alert(`${item} is at index ${index} in ${array}`);
});

//현년도를 가져와서
//만나이
var birth = prompt("생년월일을 입력하세요", "1980-07-15");

function gettingOriginalAge(birth) {
const today = new Date(); //현재 날짜[:5]
let age = today.getFullYear() - Number(birth.slice(0, 4)) + 1;
//2022-1980 + 1 = 43
alert(age);
alert(Number(birth.slice(0, 4)));

let mon = today.getMonth() + 1 - Number(birth.slice(5, 7)); //getMonth()는 0-11로 출력되므로 +1
//10-7 =3
//생일이 지났고
if (
mon < 0 ||
(mon === 0 && today.getDate() < Number(birth.slice(8, 10)))
) {
return (age = age - 1); //생일이 안지났을 경우 1을 빼줍니다.
} else {
return age;
}
}

const currentDate = new Date();
var currentYear = currentDate.getFullYear();
// alert(currentYear);
var birthYear;
var age;

birthYear = prompt("태어난 연도를 입력하세요. (YYYY)", "");
age = currentYear - birthYear + 1;
document.write(currentYear + "년 현재<br>");
document.write(
birthYear + "년에 태어난 사람의 나이는 " + age + "세입니다.<br>"
);
function 만나이계산() {
return;
}
계산된만나이 = gettingOriginalAge(birth);
document.write(`만나이는 ${계산된만나이} 세입니다.<br>`);
*/
</script>

<script>
/*
var i;
var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
var count = 0;

if (userNumber !== null) {
document.write(
'<div class="container"><table class="table"><thead><tr><th scope="col">연번</th><th scope="col">3의 배수</th></tr></thead><tbody>'
);
for (i = 0; i < userNumber; i++) {
if (i % 3 === 0) {
count++;
// document.write(i);
// document.write("<br>");
document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
}
}
// document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
document.write("</tbody></table><p></p></div>");
document.write(
`<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
);
}
*/
</script>

<!-- <script>
var session = prompt("관심 언어를 선택해 주세요. 파이썬, 자바스크립트, 자바");

switch (session) {
case "파이썬" : document.write("<p>파이썬 세션은 <strong>201호</strong>에서 진행됩니다.</p>")
break;
case "자바스크립트" : document.write("<p>자바스크립트 세션은 <strong>203호</strong>에서 진행됩니다.</p>");
break;
case "자바" : document.write("<p>자바 세션은 <strong>205호</strong>에서 진행됩니다.</p>")
break;
default: alert("잘못 입력했습니다.");
location.reload();
}
</> -->

<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
crossorigin="anonymous"
></script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
<script>
let obj = {
key1: "value1",
key2: "value2",
key3: "value3",
key4: "value4",
key5: "value5",
key6: "value6",
key7: "value7",
key8: "value8",
};

let objKeys = Object.keys(obj);
console.log(objKeys);

let objValues = Object.values(obj);
console.log(objValues);

const copy1 = Object.assign({}, obj);
Object.keys(copy1).forEach(function (key, index) {
copy1[key] += "입니다";
});
console.log("깊은복사후적용=>",copy1);

const copy2 = Object.assign({}, obj);
for (var key in copy2) {
if (copy2.hasOwnProperty(key)) {
copy2[key] += "입니까?";
}
}
console.log("깊은복사후적용=>",copy2);

// => { 'a': 2, 'b': 4, 'c': 6 }
let objJSON = JSON.stringify(obj);
console.log(objJSON);

/*
let users = [
{ id: 1, name: "John" },
{ id: 1, name: "Pete" },
{ id: 1, name: "Mary" },
];

let user = users.filter((item) => item.id == 1);
alert(user[1].name); // Joh

["Bilbo", "Gandalf", "Nazgul"].forEach((item, index, array) => {
alert(`${item} is at index ${index} in ${array}`);
});

let asdf = ["Bilbo", "Gandalf", "Nazgul"];

asdf.forEach(function (item, index, array) {
alert(`${item} is at index ${index} in ${array}`);
});

//현년도를 가져와서
//만나이
var birth = prompt("생년월일을 입력하세요", "1980-07-15");

function gettingOriginalAge(birth) {
const today = new Date(); //현재 날짜[:5]
let age = today.getFullYear() - Number(birth.slice(0, 4)) + 1;
//2022-1980 + 1 = 43
alert(age);
alert(Number(birth.slice(0, 4)));

let mon = today.getMonth() + 1 - Number(birth.slice(5, 7)); //getMonth()는 0-11로 출력되므로 +1
//10-7 =3
//생일이 지났고
if (
mon < 0 ||
(mon === 0 && today.getDate() < Number(birth.slice(8, 10)))
) {
return (age = age - 1); //생일이 안지났을 경우 1을 빼줍니다.
} else {
return age;
}
}

const currentDate = new Date();
var currentYear = currentDate.getFullYear();
// alert(currentYear);
var birthYear;
var age;

birthYear = prompt("태어난 연도를 입력하세요. (YYYY)", "");
age = currentYear - birthYear + 1;
document.write(currentYear + "년 현재<br>");
document.write(
birthYear + "년에 태어난 사람의 나이는 " + age + "세입니다.<br>"
);
function 만나이계산() {
return;
}
계산된만나이 = gettingOriginalAge(birth);
document.write(`만나이는 ${계산된만나이} 세입니다.<br>`);
*/
</script>

<script>
/*
var i;
var userNumber = parseInt(prompt("몇 까지 3의 배수를 찾을까요?", "100"));
var count = 0;

if (userNumber !== null) {
document.write(
'<div class="container"><table class="table"><thead><tr><th scope="col">연번</th><th scope="col">3의 배수</th></tr></thead><tbody>'
);
for (i = 0; i < userNumber; i++) {
if (i % 3 === 0) {
count++;
// document.write(i);
// document.write("<br>");
document.write(`<tr><th scope="row">${i}</th><td>${i}</td></tr>`);
}
}
// document.write("<p>"+ userNumber + "까지 3의 배수의 갯수 : " + count + "</p>");
document.write("</tbody></table><p></p></div>");
document.write(
`<p>${userNumber}까지 3의 배수의 갯수 : ${count} 입니다</p>`
);
}
*/
</script>

<!-- <script>
var session = prompt("관심 언어를 선택해 주세요. 파이썬, 자바스크립트, 자바");

switch (session) {
case "파이썬" : document.write("<p>파이썬 세션은 <strong>201호</strong>에서 진행됩니다.</p>")
break;
case "자바스크립트" : document.write("<p>자바스크립트 세션은 <strong>203호</strong>에서 진행됩니다.</p>");
break;
case "자바" : document.write("<p>자바 세션은 <strong>205호</strong>에서 진행됩니다.</p>")
break;
default: alert("잘못 입력했습니다.");
location.reload();
}
</> -->

<script
src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
crossorigin="anonymous"
></script>
</body>
</html>
```

### 계산기

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Bootstrap demo</title>
<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"
rel="stylesheet"
integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi"
crossorigin="anonymous"
/>
</head>
<body>
    <div class="container">
      <div class="calculator">
        <div class="calculator__display--for-advanced">0</div>
        <div class="calculator__buttons">
          <div class="clear__and__enter">
            <button class="clear">AC</button>
            <button class="calculate">Enter</button>
          </div>
          <div class="button__row">
            <button class="number">7</button>
            <button class="number">8</button>
            <button class="number">9</button>
            <button class="operator">+</button>
          </div>
          <div class="button__row">
            <button class="number">4</button>
            <button class="number">5</button>
            <button class="number">6</button>
            <button class="operator">-</button>
          </div>
          <div class="button__row">
            <button class="number">1</button>
            <button class="number">2</button>
            <button class="number">3</button>
            <button class="operator">*</button>
          </div>
          <div class="button__row">
            <button class="number double">0</button>
            <button class="decimal">.</button>
            <button class="operator">/</button>
          </div>
        </div>
      </div>
    </div>
</body>
</html>
```

``` css
.container {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.calculator {
  background-color: #06597a;
  width: 350px;
  height: 500px;
  border-radius: 10px;
  padding: 10px 20px;
  border: solid 6px #ffffff;
}
.calculator__display--for-advanced {
  background-color: #f09393;
  height: 100px;
  width: 100%;
  border-radius: 10px;
  font-size: 30px;
  text-align: center;
  vertical-align: middle;
  padding: 25px 15px;
  overflow: hidden;
  overflow-wrap: break-word;
}
.calculator__buttons {
  background-color: #ffffff;
  width: 100%;
  height: 330px;
  margin-top: 10px;
  padding: 10px;
  border-radius: 10px;
  font-size: 25px;
}
.clear__and__enter {
  text-align: center;
  height: 50px;
  margin: 10px;
  border-radius: 10px;
  background-color: #ffffff;
}
.clear__and__enter > button {
  border-radius: 10px;
  width: 125px;
  height: 50px;
  margin: 0px 0px;
  background-color: #f09393; 
  cursor: pointer;
  outline: none;
  border: 0px solid #30bb98;
}
.button__row {
  border-radius: 10px;
  text-align: center;
  height: 50px;
  margin: 10px;
  background-color: #ffffff;
}
.button__row > button {
  width: 60px;
  height: 50px;
  border-radius: 10px;
  cursor: pointer;
  outline: none;
  background-color: #bdb2b2;
}
.button__row > .operator {
  color: #ffffff;
  background-color: #313132;
}
.button__row > .double {
  width: 125px;
}
.button__row > .isPressed {
  background-color: #00da75;
}
```

``` javascript
<script>
const calculator = document.querySelector('.calculator'); // calculator 엘리먼트와, 그 자식 엘리먼트의 정보를 모두 담고 있음.
const buttons = calculator.querySelector('.calculator__buttons'); // calculator__keys 엘리먼트와, 그 자식 엘리먼트의 정보를 모두 담고 있음.
const operator = document.querySelector('.calculator__operator'); // calculator__operator 엘리먼트와, 그 자식 엘리먼트의 정보를 모두 담고 있음.
const display = document.querySelector('.calculator__display--for-advanced'); // calculator__display 엘리먼트와, 그 자식 엘리먼트의 정보를 모두 담고 있음.
<br>
function calculate(n1, operator, n2) {
  let result = 0;
  if(operator === '+') {
    result = Number(n1) + Number(n2); // '+'버튼을 눌렀을 때
  }
  else if(operator === '-') {
     result = Number(n1) - Number(n2); // '-'버튼을 눌렀을 때
  }
  else if(operator === '*') {
     result = Number(n1) * Number(n2); // '*'버튼을 눌렀을 때
  }
  if(operator === '/') {
     result = Number(n1) / Number(n2); // '/'버튼을 눌렀을 때
  }
  return String(result);
}
<br>

let firstNum = '';
let operatorForAdvanced = '';
let previousKey = '';
let previousNum = '';
<br>

buttons.addEventListener('click', function (event) {
  const target = event.target; // 클릭된 HTML 엘리먼트의 정보가 저장되어 있음.
  const action = target.classList[0]; // 클릭된 HTML 엘리먼트에 클레스 정보를 가져옴.
  const buttonContent = target.textContent; // 클릭된 HTML 엘리먼트의 텍스트 정보를 가져옴.
<br>
  if (target.matches('button')) {
    if (action === 'number') { //클릭된 HTML 엘리먼트의 클래스 네임이 'number'라면
      if (display.textContent === '0' && operatorForAdvanced === '') {
        display.textContent = buttonContent;
        firstNum = display.textContent // 첫번째 숫자를 변수에 할당
      } // 기존 계산기 숫자가 0이고, 오퍼레이터 버튼이 안눌린 상태의 분기
      else if (display.textContent !== '0' && operatorForAdvanced === ''){
        display.textContent = display.textContent + buttonContent;
       // textContent는 문자열이기 때문에 기존 계산기에서 보여지는 숫자에 +연산자로 구현 
        firstNum = display.textContent ;
      } // 기존 계산기 숫자가 0이 아니고, 오퍼레이터 버튼이 안눌린 상태의 분기
        // ex) 15를 누르기 위해 1을 누른 상태의 분기(두자리 연속 누르기 위한 코드)
      else if (display.textContent !== '0' && operatorForAdvanced !== '') {
        if(previousKey === operatorForAdvanced) {
          display.textContent = buttonContent;
          previousKey = display.textContent; 
          // 직전키를 변수에 할당 (직전키가 오퍼레이터냐 숫자냐에 따라 계산기의 다양한 기능을 구현하기 위함)
          previousNum = display.textContent; // 직전 숫자를 변수에 할당
        } // 기존 계산기 숫자가 0이 아니고, 오퍼레이터 버튼이 눌린 상태의 분기
          // ex) 15+7을 하기 위해 15와 +를 누른 상태(두번째 숫자를 누르기 위한 코드)
        else if(previousKey !== operatorForAdvanced) {
          display.textContent = display.textContent + buttonContent;
          previousNum = display.textContent;
        } // ex) 15+17을 하기 위해 15와 +, 1을 누른 상태(17을 완성하기 위한 코드)
      }    
    }
<br>
    if (action === 'operator') { // //클릭된 HTML 엘리먼트의 클래스 네임이 'operator'일때 분기
      operatorForAdvanced = buttonContent; // 오퍼레이터 누를 때 누른 텍스트 정보 할당
      previousKey = operatorForAdvanced; // 직전키에 오퍼레이터 텍스트 정보 할당
    }
<br>
    if (action === 'clear') { // AC(초기화) 버튼을 누를 때 분기
      display.textContent = '0';
      firstNum = '';
      previousNum = '';
      operatorForAdvanced = '';
      previousKey = '';
    }
<br>
    if (action === 'calculate') { // Enter(계산) 버튼을 누를 때
      if(firstNum !== '' && operatorForAdvanced === '') {
        display.textContent = firstNum;
      }
      else if(firstNum !== '' && previousNum === '') {
        display.textContent = calculate(display.textContent, operatorForAdvanced, display.textContent)
      } // 기존에 작성했던 calculate 함수를 이용하여 계산 상황에 따른 전달인자와 함께 호출
      else if(previousKey === display.textContent){
        display.textContent = calculate(firstNum, operatorForAdvanced, previousNum)
        //   if(operatorForAdvanced === '+') {
        //   display.textContent = String(Number(firstNum) + Number(previousNum));
        // } else if(operatorForAdvanced === '-') {
        //   display.textContent = String(Number(firstNum) - Number(previousNum));
        // } else if(operatorForAdvanced === '*') {
        //   display.textContent = String(Number(firstNum) * Number(previousNum));
        // } else if(operatorForAdvanced === '/') {
        //   display.textContent = String(Number(firstNum) / Number(previousNum));      
        // } // 기존에 작성했던 하드코딩..!       
       } 
       else if(previousKey !== display.textContent && previousNum !== '') {
        display.textContent = calculate(display.textContent, operatorForAdvanced, previousNum)
       }   
       else if(previousKey !== display.textContent && previousNum === '') {
        display.textContent = firstNum;
       }
     }
   }
});

</script>
```
