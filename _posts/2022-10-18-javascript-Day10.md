---
layout: post
title: "Javascript 10일차"
description: "Javascript 10일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/18/
---
# 10일차

## 숫자형
Infinity : 무한대


## NULL vs Undefined
링크 : https://velog.io/@iamhayoung/JavaScript-undefined-null%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90
null : 의도적으로 값이 없음을 표현할 때 사용하는 코드
<br>
데이터의 존재여부를 체크할 때에 사용

undefined : 정의되지 않은 것을 나타내며 데이터가 존재하지 않음을 의미한다
<br>
변수 또는 함수가 선언은 되었으나 값이 할당되지 않았다,
혹은 데이터 그 자체가 존재하지 않는다=정의되지 않았다는 것을 알려주는 지표


### 정리
변수를 선언하고 빈박스를 지정해준게 null, 변수만 선언한게 undefined
->그러므로 null은 타입이 object이고 undefined는 undefined이다.


## Template literals
Template literals : 파이썬에서 fstring의 기능을 하는 자바스크립트의 기능을 말한다.


## 연산자
### 증감연산자(++ / --) : 변수값을 +1을 해주거나 -1을 해줄때 사용하며 ++/--의 위치에 따라서 계산의 순서가 달라진다.
링크 : http://www.tcpschool.com/javascript/js_operator_incAndDec

```javacript
var x = 10;            

var y = x-- + 5 + --x;

// x = 8, y = 23
```
이때 다음 사진과같이 계산의 순서가 결정되고 증감연산자에 따라서 값이 달라짐을 알 수 있다.(연산자의 곱셈과 나눗셈이 들어가는 경우)

### 비교연산자
!== : 형까지 포함해서 동일한지 판별할때 사용

### 논리연산자
!! : !을 한번 사용했을때 나오는 논리의 역을 반환해준다.(왜 쓰는걸까?)


### 삼항연산자
if-else문과 동일한 기능을 하는 방식이다.

조건 ? 참 : 거짓;으로 구성되어있다.

사용하는 이유 : 코드를 간결하게 만들기 위해서 사용한다.

### 비트연산자
십진수를 이진수의 연산법칙으로 바꿔서 계산하고 십진수로 바꾼다.


## 자료형
객체의 모양 그대로를 문자로 바꿀때 JSON stringfy를 사용한다.
->왜 "5"를 숫자로 인식하는것일까? object라서인가?

## 배열
배열값을 벗어난 범위의 값은 undefined로 출력된다.

## 객체
링크 : https://hanamon.kr/javascript-%EA%B0%9D%EC%B2%B4-%EA%B8%B0%EC%B4%88/
객체 : 키와 벨류로 이루어진 데이터의 집합

프로퍼티 : 객체의 상태를 나타내는 값
메소드 : 객체를 조작하는 함수

### 단축속성명
객체 생성시 변수로 입력해서 만들려고 사용한다

## 심볼
심볼이란 고유값을 생성할때 사용한다.



## Argument
argumnet란 배열로 입력되지 않은 값을 함수에서 배열로 인식시켜서 사용하려할 때 사용한다.

예시
``` javascript
<script>
function sum(){
    var i, _sum = 0;    
    for(i = 0; i < arguments.length; i++){
        document.write(i+' : '+arguments[i]+'<br />');
        _sum += arguments[i];
    }   
    return _sum;
}
document.write('result : ' + sum(1,2,3,4));
</script>
```

```javascript
function sum() {
  var total = 0;
  for (var i = 0; i < arguments.length; i++) {
    total += arguments[i];
  }
  console.log(arguments instanceof Array);
  return total;
}

var sumOf1to3 = sum(1, 2, 3);
console.log(sumOf1to3);

function testArg() {
  var newArr = Array.prototype.slice.call(arguments);
  console.log(newArr);
  console.log(newArr.indexOf('b'));
  console.log(arguments.indexOf('b'));
}

testArg('a', 'b');
```
argument는 배열이 아니므로 indexof를 사용할때 대응되는 값이 없기 때문에 사용이 블가능하다(?)


## 지역변수 / 전역변수


## 리턴객체
객체에 담겨있는 함수 호출

## 딜레이
setTimeout()

## 프로토타입(prototype)

## 클래스

### 메소드

### This


## 모듈


# javascript 예제들
링크 : https://codingschool.info/content/prob_js.php?prob_type=list&cat=total