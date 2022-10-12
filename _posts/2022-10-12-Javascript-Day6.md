---
layout: post
title: "Javascript 6일차"
description: "Javascript 6일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/12/
---
# 6일차
(DO it교재 441,509,513)
## 15장 함수와 이벤트
함수 : 동작해야할 목적대로 묶은 명령

### 더하기 함수
```javascript
# 교재
<script>
  function addNumber(a,b){
    var sum = a+b;
    alert(sum)
  }
</script>

# 강사님
<script>
  function addNumber(a,b){
    let result = a+b;
    return result;
  }
  console.log(addNumber(3,5));
</script>
```
함수 선언과 함수 호출은 작성 순서상관없이 작동한다 그러나 함수 선언을 먼저 해주는 방식을 선호한다

### 범위 스코프
변수를 끌어다 쓸 수 있는 범위를 범위 스코프라고 한다
(지역,전역) / (로컬, 글로벌)

전역변수는 지역변수를 대체할수 있지만 지역변수는 전역변수를 대체할 수 없다

#### 호이스팅
호이스팅이란 끌어올림을 의미한다 즉, 순서대로 처리되지 않음을 의미한다
-> 선언이 되기 전에는 쓸수가 없다. 선언된 부분의 순서를 끌어올려서 사용하는 것이기 때문

### 함수에서 변수 구분
전역변수는 최소한으로 사용하고 이름관리를 잘해라
var 변수는 함수의 시작부분에서 선언해라(전역변수로 사용)


var : 재할당, 재선언 가능
let : 재할당은 가능, 재선언은 불가능
const : 상수로서 재선언도 불간으 
-> var는 하위호환성 때문에 남겨져있고 현재는 let을 많이 사용한다

<!-- let
재할당은 가능, 재선언은 불가

들어있는 값을 바꾸는건 가능

같은이름으로 변수를 선언하는건 불가

let asdf;
asdf=10;

asdf=20;

let asdf;
asdf=30;

var asdf; -->

매개변수 : 중간 주개변수로 실제값을 인수한다.

return 함수는 무조건 리턴이 있어야한다
js 함수에서 기본값 지정하기

입력값 검증방법(validation)
검증함수(입력값)을 따로 만들어줘야하고
리턴한것을 함수로 한다


### 익명함수
함수 명이 없는 함수를 익명함수라고 한다

즉시실행함수 : 함수를 실행하는 순간 함수를 정의한다, 또한 실행하는 순간에 해석한다
```
function 함수이름(){
  return ;
}
```

화살표 함수 : 익명함수로 만들고 그것을 변수에 지정해주는 함수
```
let func1 = () =>{

}

or

=(a)=> {
  return ;
}
```


### 이벤트와 이벤트 처리(15-6)
구글 : js event를 검색해서 Docs나 library를 가져올 수 있다<br>
이벤트 전체 리스트 : https://perimeterx.github.io/map-events-website/ 에 있다<br>


폼이벤트 : focus 정도만 주로 사용하나

폼의 DOC(https://getbootstrap.com/docs/4.3/components/forms/)


#### 이벤트 처리기
이벤트핸들러 = 이벤트 처리기 : 이벤트가 발생하면 처리하는 함수를 이르는 명칭


현재 날짜 및 시간 생성하기
``` html


```





폰트어썸(https://fontawesome.com/) : <br>
Chart js : 차트를 그리기 쉽게 도와주는 템플릿