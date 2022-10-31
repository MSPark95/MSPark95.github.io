---
layout: post
title: "Javascript 14일차"
description: "Javascript 14일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/21/
---
# 14일차

## node 설치
노드
노드 패키지 메니저 npm
npm 인스톨 익스프레스 제너레이터
익스프레스 프로젝트 만들어줌
프로젝트 만듬 템플릿엔진 ejs

C:\Users\내계정\expressproject
SET DEBUG=expressproject:* & npm start

http://localhost:3000/

다시 접속할 때

1. 윈도우 옆 돋보기로 node pormpt 실행
2. C:\users\내계정\expressproject 위치로 이동
3. SET DEBUG=expressproject:*& npm start 입력


## 순서
node command prompt 버전 확인
node -v

express generator 설치(익스프레스 프로젝트 만들어줌)
npm install express-generator -g.

익스프레스 플젝 생성(템플릿 엔진 ejs)
express expressproject --view=ejs

익스프레스 플젝으로 이동
cd expressproject

인스톨
npm install

디버그 모드로 로컬호스트 실행
SET DEBUG=expressproject:* & npm start

주소창에 입력
http://localhost:3000/

프로젝트 파일이 잘 생성됐는지 확인하는 방법
C:\Users\내계정\expressproject

다시 할 때
1. 윈도우 옆 검색창 돋보기에 node prompt 실행
2. cd로 경로 이동 C:\Users\내계정\expressproject
3. SET DEBUG=expressproject:* & npm start



mvc 디자인패턴
m 모델 -> 디비
v 뷰 -> 화면 ejs
c 컨트롤러 -> 논리, 비지니스

r 라우터 -> 경로

1. html 해석 문법
2. ejs 템플릿엔지 해석 문법
변수받는거 <%= title %>
조건문 <% if (user.email) { %>
반복문
인클루드 <%- include('partials/navbar.ejs', data) %>

3. pug 템플릿엔지 해석 문법



https://mockaroo.com/

## 인코딩과 디코딩
인코딩 parse
디코딩 stringify

js JSON.parse() 디코딩
js JSON.stringify() 인코딩

php json_encoding() 인코딩
php json_decoding() 디코딩

python json.dump() 인코딩
python json.loads() 디코딩

## express 활용
병원홈페이지 제작
https://github.com/INVIII/QuroCare


### ip주소 확인 사이트
https://www.findip.kr/



### 주소
C:\laragon\bin\apache\httpd-2.4.35-win64-VC15\conf

### ip관련
주소 <-> ip

도메인네임 -> 아이피

아이피로 서버를 찾아간다

DNS서버

가비아 까페24

co.kr
com


돈을 주고 도메인을 사면
아이피 웹호스팅 서버하나에 나말고도 여럿이 같이쓴다
아이피 코로케이션 서버를 하나 통으로 임대
공유기에
포트포워딩 80 데이터베이스 mysql 3306 포트포워딩
포트포워딩 3000 데이터베이스 mysql 3306 포트포워딩
80 -> 3000
고정라우팅


textesdf.p-e.kr

독립서버운영

myhomeeee1.co.kr 등록 -> 210.99.188.4
myhomeeee2.co.kr 등록 -> 210.99.188.4
myhomeeee3.co.kr 등록 -> 210.99.188.4
내가만드 웹이 오픈
ip
하나의 IP 하나의 웹 여러

아파이 웹서버

버추어호스트
myhomeeee1.co.kr -> 1번디렉토리
myhomeeee2.co.kr -> 2번디렉토리
dfddf.dfd.df -> dfd디렉토리

설정관련해서 httpd.conf

버추어디렉토리


버추어호스팅

공인IP
210.99.188.4
공유로 사설로 할당
192.168.0.255


https://www.heidisql.com/