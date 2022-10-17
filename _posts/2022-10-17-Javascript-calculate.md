---
layout: post
title: "Javascript 계산기"
description: "Javascript 계산기"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/17/
---
# 계산기 만들기

참고 : url1(https://velog.io/@duboo/%EB%B0%94%EB%8B%90%EB%9D%BC-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%A7%8C%EB%93%9C%EB%8A%94-%EA%B3%84%EC%82%B0%EA%B8%B0)<br>
참고 : url2(https://aosceno.tistory.com/m/615)<br>
참고 : url3(https://taiyakee.tistory.com/m/66)

``` html
<!DOCTYPE html>
<html lang="kr">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style1.css">
  <title>Document</title>
</head>
<body>
  <div class="calc">
		<div class="display-container">
         <div id="steps" class="off">0</div>
          <div class="display">0</div>
    </div>
      <div id="area-btn">
        <button class="clear">AC</button>
        <button class="operation">()</button>
        <button class="operation">%</button>
        <button class="operation">&#247</button>
        <button class="number">7</button>
        <button class="number">8</button>
        <button class="number">9</button>
        <button class="operation">×</button>
        <button class="number">4</button>
        <button class="number">5</button>
        <button class="number">6</button>
        <button class="operation">-</button>
        <button class="number">1</button>
        <button class="number">2</button>
        <button class="number">3</button>
        <button class="operation">+</button>
        <button class="number">&#177</button>
        <button class="number">0</button>
        <button class="number">.</button>
        <button class="result">=</button>
      </div>
    </div>

    <script>

    </script>
</body>
</html>
```

```css
@charset "utf-8";
*{margin:0;padding:0;box-sizing:border-box;}
html,body{
    display:flex;flex-flow:column nowrap;
    justify-content:center; align-items:center;
    width:100%;min-height:100vh;
    background:white;
    font-size:18px;
}
button{font-family:inherit;cursor:pointer;}
button:hover{filter:brightness(80%);}
button:focus{filter:brightness(60%);}
 
/* 계산기 */
.calc{
  position:relative;
  width:95%; max-width:300px;
  background:rgba(255,255,255,.1);
  border-radius:4px;
  box-shadow:5px 5px 1rem rgba(0,0,0,.2);
}

/* 숫자 계산 화면 */
.display{
  position:relative;
  width:100%;
  background:rgba(255,255,255,.1);
  border-bottom:1px solid rgba(0,0,0,.3);
  text-align:right;
}
#steps{
  position:relative;
  width:100%;
  padding:1.5rem 1.25rem .5rem;
  font-size:14px; color:rgba(255,255,255,.4);
}

  #steps.off{opacity:0;}
#display{
  display:block;position:relative;
  width:100%; height:auto;
  white-space:normal;
  word-break:break-all;
  padding:0 1rem; padding-bottom:1.25rem;
  background:transparent;
  border:none;
  text-align:right;font-family:inherit;font-size:2rem; color:#fff;
}

/* 버튼 영역 */
#area-btn{
  position:relative;display:flex;flex-flow:row wrap;
  justify-content:space-between;align-items:flex-start;
}

/* 버튼 - 숫자 */
.number{
  display:flex;flex-flow:row wrap;
  position:relative;
  width:75%;

}
.number{
  display:block;
  width:33.33%; aspect-ratio:1/1;
  border:1px solid rgba(0,0,0,.2);
  background:#707070;
  font-size:inherit; color:rgba(255,255,255,1);
}
/* .num[data-val="0"]{width:66.66%; aspect-ratio:0;} */
.number[data-val="-1"],
.number[data-val="."]{background:rgba(255,255,255,.1);}

/* 버튼 - 연산 */
.operation{
  position:relative;
  width:25%;
}
.operation{
  display:block;
  width:100%; aspect-ratio:1/1;
  background:rgba(255,255,255,.1);
  border:1px solid rgba(0,0,0,.2);
  font-size:1.5rem; color:#fff;
}
.clear{
  display:block;
  width:100%;aspect-ratio:1/1;
  background:rgba(36, 55, 165, 0.1);
  border:1px solid rgba(0,0,0,.2);
  font-size:1rem; color:#fff;
}

/* = 버튼 */
.result{
  display:block;
  width:100%; aspect-ratio:1/.33;
  background:rgba(93, 128, 241, 0.3);
  border:1px solid rgba(0,0,0,.2);
  font-size:2rem; font-weight:bold; color:#fff;
  mix-blend-mode:hard-light;
}
```