---
layout: post
title: "자바스크립트 4일차"
description: "자바스크립트 4일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/07/
---
#  전역내장함수

rout 파일을 사용하기 위해서는
```javascript
rout.get('/index2.html', function(req,res,next){
  res.sendFile("index2.html파일경로")
})
```
을 js파일에 추가해줘야한다.

## 동적페이지
bootstrap

tailwindcss

머터리얼


### Escape문자(계획문자)





# 자바스크립트로 홈페이지 꾸미기
```javascript
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
    <div id="myId"
      style="
        background-image: url('https://cdn.pixabay.com/photo/2022/09/26/15/02/mountains-7480902_960_720.jpg');
        height: 500px;
      "
    >
    
      <p></p>
    </div>
    <script>
      document.write("<script>alert('dfsfds');</script>");

      var reply = confirm("정말 배경 이미지를 바꾸겠습니까?");

      if (reply) {
        
        var currentsyle = document
        .getElementById('myId')
        .getAttribute('style');

        // var currentStyle = document.getElementById('myId').getAttribute('style');

        //alert(currentStyle);
        currentStyle = "background-image: url('https://cdn.pixabay.com/photo/2022/09/25/09/58/houses-7477950_960_720.jpg');" + "\n" + "height: 200px;"
        //document.getElementById('myId').getAttribute('style') = currentStyle
        document.getElementById("myId").style.backgroundImage="url('https://cdn.pixabay.com/photo/2022/09/25/09/58/houses-7477950_960_720.jpg')";
      } else {

      }

      var size = prompt("크기는 얼마로");
      alert(`${size}를 입력하였습니다. ${typeof(size)}`);
      document.getElementById("myId").style.height = size;

    </script>

    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```


### 정규표현