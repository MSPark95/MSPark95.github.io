---
layout: post
title: "자바스크립트 2일차"
description: "자바스크립트 2일차"
categories: [demo]
tags: [demo, jekyll]
redirect_from:
  - /2022/10/05/
---

# 자료형
null타입

null값을 정의하는 특별한 유형

undefined

값이 할당되지 않은 자료형


## 객체
자료구조 자료형으로서 객체를 의미한다

{"":"", "":""}

xml -> json -> restapi로 규약이 바뀌었다

## 여러 언어를 여러 통신으로 자료 전달하는 방법
"ㅇㄹㅇ"를

파이썬 어레이 리스트 np.array()<br>
["ㅇㄹㅇㄴㄹ","ㅇㄹㄴㄹ"]

("ㅇㄹㅇㄹ","ㅇㄹㅇ")

딕셔너리 맴 / 해시맵<br>
{"ㅇㄹㅇ":"ㅇㄹㅇ", "ㅁㅇㄹㄴ":"ㅇㄹㅇㄹ"}

판다스
데이터 프레임워크

## 자료형을 확인하는 방법

type() 혹은 typeof()를 사용한다

단축키는 ctrl+D 혹은 Art+Shift+I이다

아주 오래전에 만들어진 규칙이기 때문에 하위 호환성을 유지하려고 사용중

-----------------

## alert prompt conform 상호작용

창안에 창을 넣는 기능 : iframe 기능을 많이 사용했으나 보안이나 여러 문제가 발생하여서 잘 사용하지 않는다(지양하도록 권장된다)

그래서 현재는 모달로 대체하여 사용한다

### 프롬프트
result=prompt(title);

입력값을 표시하는 방법
~~~~~~ javascript
let name=prompt("이름을 입력해주세요","정대호")<br>
alert(`제이름은 ${name}입니다.`)
~~~~~~

확인/ 취소 선택상자 생성방법
~~~ javascript
let isBoss = confirm("당신이 주인인가요?")
alert(isBoss)
~~~


alert : 메시지를 보여주는 기능<br>
prompt :입력칸을 생성하는 기능<br>
confirm : 선택상자를 생성하는 기능<br>

### 형변환
자바스크립트 : 동적 타이핑 언어 -> 자동적으로 자료형변환이 되는 언어

~~~javascript
문자형 형변환 : String(value);
숫자형 형변환 : Number(value);
불린형 형변환 : Boolean(value);

폼을 통해서 받는다

html <br>
<form>
  <input type="text">
</form>
이러한 구조는 숫자여도 문자형으로 받아들인다

*주의 : 문자열 "0"은 true입니다.
PHP 등의 일부 언어에선 문자열 "0"을 false로 취급합니다.
그러나 자바스크립트에선 비어 있지 않은 문자열은 언제나 true입니다.
~~~

<!-- 파이썬
str(),int()등과 같이 형변화를 해줘야한다 -->

## 연산자

단 항 

이 항 : 두개

삼항연산자 : 세개의 연산자를 이용한 것

피연산자 : 연산자의 대상이 되는 것

인수

~~~
나머지 %
거듭 **(파이썬에서는 ^)
+ 덧셈 혹은 문자열 연결시 사용(파이썬고나 자바스크립트 모두 동일)

PHP에서는 문자열 연결시 .을 사용
~~~

### 연산자 우선순위
#### 할당 연산자

= : 좌우가 중요한 연산자로 우측의 값을 좌측의 변수에 넣는다는 의미
~~~ javascript
let a=1;
let b=2;

let c=3-(a=b+1);

alert(a); //3
alert(c); //0
~~~

#### 할당연산자 체이닝

객체.객체.객체.으로 된 구조

~~~javascript
let a,b,c;

a=b=c=2+2;

alert(a); //4
alert(b); //4
alert(c); //4
~~~

#### 복합할당 연산자
~~~ javascript
n=n+5
n+=5

+=
-=
*=
~~~

#### 증가감소 연산자

c스타일의 포문을 외워라
~~~ c
for (i=0;i<변수.length;i++){
}
for (i=0;i<count(변수);$i++){
}
~~~
++ : 처음것을 한번 넣어주고 더하기를 시작한다

~~~javascript
let counter = 2;
2+1;
alert(counter);
~~~

#### 비트 연산자=비트와이즈연산자
~~~javascript
 & : and의 의미
 ㅣ: or의 의미
~~~

#### 쉼표연산자 : 여러줄을 한줄로 평가하도록 해주는 연산자
~~~ javascript 
for (a=1,b=3,c=a*b;a<10;a++){
  ...
}
~~~

#### 비교연산자 
>
<

==
=== : 타입까지 동일한것

!= : 같지않다


자바스크립트에서만 일어나는 기이한 현상 반직관 : 

#### 문자열 비교

사전편집(lexicographical) : 알파벳순
정확히는 사전 순이 아니라 유니코드 순이다
alert('Z'>'A'); true

다른 형을 가진 값 간의 비교(타입변환)
~~~javascript
let a=0;
alert(Boolean(a));//false

let b="0";
alert(Boolean(b));//true

alert(a==b); //true
~~~

#### 축약형 개념
조건부연산자
~~~javascript
if (조건){
  내용
}

ex)
let year=prompt('ECMAScript-2015 명세는 몇년도에 출판되었을까요?','')
if (year==2015)? alert('정답입니다!'): alert('정답이아닙니다!');
~~~

삼항연산자
~~~javascript
if (a= true){

} else if{

} else {

}
~~~

조건부 연산자는 물음표(?)로 표시한다.
피연산자가 3개이기 때문에 조건부 연산자를 '삼항(ternary) 연산자'라고 부르는 사람도 있다
참고로 자바스크립트에서 피연산자를 3개 받는 연산자는 조건부 연산자가 유일하다

#### 논리연산자
ㅣㅣ(OR), &&(AND), !(NOT)
우선순위는 ()로 표현해준다

#### nullish 병합연산자
구식 브라우저는 폴리필이 필요하다
폴리필 : 
ECMA2022

### 반목문
while

for 

M데이터베이스, V화면 C논리, 비지니스

퍼그뎀플릿, 퍼그 탬플릿 문법
장고, 장고 탬플릿 문법
플라스크 jinja2 탬플릿 문법

for if
테이블 포문 결합해서 출력

for i in range(0,len(dfsdf))

종료값은 -1이다

생략 스탭
for(::)은 무한출력이다

continue : 반복문에서 break없이 실행되도록 하는 코드

break : 반복문을 스탑시키는 코드


#### 가변변수 동적변수
red="


### 함수
함수 선언
~~~ javascript 
function showMessage(){
  alert('안녕하세요!');
}
~~~
매개변수가 없더라도 작동이 가능하다

매개변수가 있다면
이때의 변수는 스콥범위인 지역적인 변수이다
~~~ javascript 
function showMessage(name,age){
  let 소개 ='이름은 ${name}입니다 나이는 ${age}입니다';
  return 소개
}
~~~
로 동작한다

#### 함수선언문 방식
함수 표현식을 사용
~~~ javascript 
function asdf(){
 alert(dfsfs);
}

let sayHi="dfdsf";
~~~


파이썬 람다와 비슷하다
익명함수
자바스크립트에서는 콜백함수가 중요하다.
재귀적:어려운 표현
~~~ javascript 
function adfs((function){
  return dfdf;
)}
~~~

함수의 결과를 다시 함수로 넣는다

~~~ javascript 
function ask(question,yes,no){
  if (confirm(question)) yes()
  else no();
}

function showOk(){
  alert("동의하셨습니다.");
}

function showCancel(){
  alert("취소버튼을 누르셨습니다.");
}

ask("동",function(){
  alert("동의");
}, function(){
  alert("취소");
});


코딩하는 디자인 패턴이 자주 사용되니 중요하다
콜백이 이루어진 함수
ask("동의하십니까?", showOk, showCancel)

콜백함수를 이용하는 코딩패턴
ask("질문?",ㄹfunction(){
  function(){
    function(){

    }
  }
}, function(){
  alert("취소")
});
~~~

함수 선언문은 전역함수로 정의되고 함수표현은 지역함수로 정의된다

화살표함수


### 변수의 2가지 유형
1. 후위형=postfix<br>
  
2. 전위형=prefix

이 두가지는 더한 다음 처음 것을 넣을지 처음 것을 넣은 뒤에 더할지의 차이이다