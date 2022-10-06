---
layout: post
title: "자바스크립트 3일차"
description: "자바스크립트 3일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/06/
---

# 화살표 함수
화살표 함수
변수에 함수를 넣어주는것
```javascript
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
```


## 엄격모드
하위 호환성을 위해서 유지하고 있는 모드이다 클래스와 같은 몇몇에서는 자동으로 엄격모드를 포함하고 있다


# Chrome에서 디버깅



## 리터럴과 프로피티

연관배열을 할때는 ""를 사용한다.
``` javascript
<script>
  let obj={"정우빈:팀장","문창일:팀원1","박문수:팀원2"};
    alert();
</script>
```
delete 연산자를 사용하면 프로피티를 삭제할 수 있다.
프로피티의 끝은 쉼표로 끝날 수 있다

## obj관련
```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>안녕하세요</h1>
    <script>
      let obj = {
    서울특별시:[
        "종로구", "중구", "용산구", "성동구", "광진구", "동대문구", "중랑구", "성북구", "강북구", "도봉구", "노원구", "은평구", "서대문구", "마포구", "양천구", "강서구", "구로구", "금천구", "영등포구", "동작구", "관악구", "서초구", "강남구", "송파구", "강동구"
    ],
    부산광역시:[
        "중구", "서구", "동구", "영도구", "부산진구", "동래구", "남구", "북구", "강서구", "해운대구", "사하구", "금정구", "연제구", "수영구", "사상구", "기장군"
    ],
    인천광역시:[
        "중구", "동구", "남구", "연수구", "남동구", "부평구", "계양구", "서구", "강화군", "옹진군"
    ],
    대구광역시:[
        "중구", "동구", "서구", "남구", "북구", "수성구", "달서구", "달성군"
    ],
    광주광역시:[
        "동구", "서구", "남구", "북구", "광산구"
    ],
    대전광역시:[
        "동구", "중구", "서구", "유성구", "대덕구"
    ],
    울산광역시:[
        "중구", "남구", "동구", "북구", "울주군"
    ],
    세종특별자치시:[
        
    ],
    경기도:[
        "가평군", "고양시", "과천시", "광명시", "광주시", "구리시", "군포시", "김포시", "남양주시", "동두천시", "부천시", "성남시", "수원시", "시흥시", "안산시", "안성시", "안양시", "양주시", "양평군", "여주시", "연천군", "오산시", "용인시", "의왕시", "의정부시", "이천시", "파주시", "평택시", "포천시", "하남시", "화성시"
    ],
    강원도:[
        "원주시", "춘천시", "강릉시", "동해시", "속초시", "삼척시", "홍천군", "태백시", "철원군", "횡성군", "평창군", "영월군", "정선군", "인제군", "고성군", "양양군", "화천군", "양구군"
    ],
    충청북도:[
        "청주시", "충주시", "제천시", "보은군", "옥천군", "영동군", "증평군", "진천군", "괴산군", "음성군", "단양군"
    ],
    충청남도:[
        "천안시", "공주시", "보령시", "아산시", "서산시", "논산시", "계룡시", "당진시", "금산군", "부여군", "서천군", "청양군", "홍성군", "예산군", "태안군"
    ],
    경상북도:[
        "포항시", "경주시", "김천시", "안동시", "구미시", "영주시", "영천시", "상주시", "문경시", "경산시", "군위군", "의성군", "청송군", "영양군", "영덕군", "청도군", "고령군", "성주군", "칠곡군", "예천군", "봉화군", "울진군", "울릉군"
    ],
    경상남도:[
        "창원시", "김해시", "진주시", "양산시", "거제시", "통영시", "사천시", "밀양시", "함안군", "거창군", "창녕군", "고성군", "하동군", "합천군", "남해군", "함양군", "산청군", "의령군"
    ],
    전라북도:[
        "전주시", "익산시", "군산시", "정읍시", "완주군", "김제시", "남원시", "고창군", "부안군", "임실군", "순창군", "진안군", "장수군", "무주군"
    ],
    전라남도:[
        "여수시", "순천시", "목포시", "광양시", "나주시", "무안군", "해남군", "고흥군", "화순군", "영암군", "영광군", "완도군", "담양군", "장성군", "보성군", "신안군", "장흥군", "강진군", "함평군", "진도군", "곡성군", "구례군"
    ],
    제주특별자치도:[
        "제주시", "서귀포시"
    ]
 };

//  alert(obj.제주특별자치도[0]);
//  alert(obj.평양);
//  alert("평양" in obj);

//  consol.log(object.values(obj));

 for (let key in obj) {
    console.log(key);
 }

//  delete obj.제주특별자치도;
//  alert(pbj.제주특별자치도[0]);

 obj.showName = function () {
    consol.log(this.경상남도[0] + "의 사투리는 ###")
 }
 obj.showName();

    </script>
  </body>
</html>
```


# Class

## 자신을 가르키는 표현
파이썬에서는 self를 사용했다<br>
그러나 Javascript에서는 this를 사용한다

```javascript
const bug = {
    name: "딱정벌레",
    species: "벌레",
    우는소리: () => console.log('${this.name}딱딱소리로 울어요'),
    숨는행동: () => console.log("${this.species}들은 숨을때 스르륵!")
}
let 처음발견한 곤충=new bug();
처음발견한 곤충.name="바퀴벌레"
처음발건한곤충.우는소리()

let 메미=new bug("매미","맴매");
매미.우는소리(),
let 개미=new 개미("개미","ㅇㅁㄹㄷㄹ");
개미.우는소리(),
let 메미=new 맹ㄻ니("매미","맴매");
매미.날;
let 메미=new ㅇㄹ매미("매미","맴매");




// console.log(alien1.name) // output: "Ali"
// console.log(bug2.species) // output: "bug"
// Robot1.sayPhrase() // output: "I can cook, swim and dance!"
// Robot2.transform() // output: "Optimus prime!"


// const alien1 = new Alien("Ali", "I'm Ali the alien!")
// // We use the "new" keyword followed by the corresponding class name
// // and pass it the corresponding parameters according to what was declared in the class constructor function

// const alien2 = new Alien("Lien", "Run for your lives!")
// const bug1 = new Bug("Buggy", "Your debugger doesn't work with me!")
// const bug2 = new Bug("Erik", "I drink decaf!")
// const Robot1 = new Robot("Tito", "I can cook, swim and dance!")
// const Robot2 = new Robot("Terminator", "Hasta la vista, baby!")

// console.log(alien1.name) // output: "Ali"
// console.log(bug2.species) // output: "bug"
// Robot1.sayPhrase() // output: "I can cook, swim and dance!"
// Robot2.transform() // output: "Optimus prime!"

```



``` javascript

```