---
layout: post
title: "Javascript 7일차"
description: "Javascript 7일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/13/
---
# 7일차

## 마무리 예제
550P
조건
1. 함수를 만든다
2. 함수의 이름은 sumMulti
3. 매개변수(x,y)
4. if 문을 사용 값 비교
5. 같으면 곱하고 다르면 합한다
6. 콘솔로그로 찍어본다

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>550P연습문제</title>
</head>
<body>
  <script>
    입력값 = prompt("값을 ,를 이용해서 입력해주세요");

    alert=('당신은 ${입력값}를 입력했습니다.');

    let list=[];
    list=입력값.split(",");
    
    function sumMulti(x,y){
      x=parseInt(x);
      y=parseInt(y);
      if (x === y) {
        result=x*y;
      } else {
        if (x != y) {
          result=x+y;
        }
       }
       return result ;
    }

    let 결과=sumMulti(list[0], list[1]);
    console.log(결과);
  </script>
</body>
</html>
```

552P
조건
1. 프롬프트 창에서 입력받은 두 수를 각각 num1, num2변수로 지정한다
2. 함수를 선언할 때 함수 명은 자유, 매개변수는 2개
3. if-else문과 비교연산자'==='를 사용
4. 두수가 같을 경우 '같습니다.'를 표시한다.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>550P연습문제</title>
</head>
<body>
  <script>
    function getNum(){
      [num1,num2]=prompt("두개의 숫자를 ,를 이용해서 입력해주세요").split(",").map(function(element){return parseInt(element);});
      console.log('${num1}, ${num2}');
      return(num1,num2);
    };
    
    function compareNumber(num1,num2){
      if (num1===num2){
        alert("${num1}과${num2}이 같습니다.");
      } else {
        if (num1<num2){
          alert("$[num2]가 더 큽니다");
        } else {
          alert("$[num1]이 더 큽니다");
        }
      }
    };
    
    getNum();
    compareNumber();

  </script>
</body>
</html>
```

## 16장 객체

### 프로퍼티, 키, 벨류, 메서드

### 내장객체, array객체
let arr["", ""]
let arr=new Array()

for in, for of
배열,배열,객체

foreach(함수)

map, filter, reduce

concat, filter ,push

기본 배열

let 무지개색깔=["빨","주"]
let 과일=["사과","배","딸기"]
어레이


조건
1. push (노초파랑보)
2. 어레이갯수는 몇개
3. 과일 중 딸기를 제거
4. concat 두어레이 합치기
5. filter 무지개색깔만 필터링

출력
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>550P연습문제</title>
</head>
<body>
  <script>
  let 무지개색깔=["빨","주"];
  let 과일=["사과","배","딸기"];
  
  무지개색깔.push("노","초","파","남","보");
  console.log(무지개색깔);
  
  console.log(무지개색깔.length);
  console.log(과일.length);

  과일=과일.splice(0,과일.indexOf("딸기"));
  console.log(과일);

  let newArr=무지개색깔.concat(과일);
  console.log(newArr);

  let filterArr=newArr.filter(element => 무지개색깔.includes(element));
  console.log(filterArr);
  </script>
</body>
</html>
```

### 달력만들기
오늘날짜
date.
만세력
js 카렌더모듈을 이용해서 달력처리
날짜별 집계 날짜 비교


link: https://nhn.github.io/tui.calendar/latest/


수업시간표
link:https://forward.nhn.com/2020/seoul/hands-on-labs/toastui.calendar-timetable/04.html



js carbon

faker프로젝트 : 더미를 만들어주는 프로젝트


### 날짜계산
라이브러리 link : https://momentjs.com/
https://forward.nhn.com/202

연습문제(두날짜의 차이 게산(환산, 변환))
조건
1. 날짜1=오늘 날짜(2022-10-13)
2. 날짜2=태어난 날짜
3. 날짜1-날짜2
4. 생후 몇일이 지났습니까?
5. 생후 몇초가 지났습니다

