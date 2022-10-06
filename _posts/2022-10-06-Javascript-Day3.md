---
layout: post
title: "자바스크립트 3일차"
description: "자바스크립트 3일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/06/
---

# 
화살표 함수
변수에 함수를 넣어주는것
~~~javascript
<script>
  let func=(a+b) =>{
    return a+b;
  }
</script>

// 한개의 인수인경우 생략이 가능하다
<script>
  let func= A =>{
    return;
  }
</script>
// 인수가 없더라도 괄호를 생략하면 안 된다.

// 연습
say("안녕하세요", let func=(a,b)=>a+b,say No)
~~~


## 엄격모드
하위 호환성을 위해서 유지하고 있는 모드이다 클래스와 같은 몇몇에서는 자동으로 엄격모드를 포함하고 있다


# Chrome에서 디버깅



## 리터럴과 프로피티

연관배열을 할때는 ""를 사용한다.
~~~ javascript
<script>
  let obj={"정우빈:팀장","문창일:팀원1","박문수:팀원2"};
    alert();
</script>
~~~
delete 연산자를 사용하면 프로피티를 삭제할 수 있다.
프로피티의 끝은 쉼표로 끝날 수 있다


~~~ javascript

~~~