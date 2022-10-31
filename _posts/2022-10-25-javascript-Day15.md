---
layout: post
title: "Javascript 15일차"
description: "Javascript 15일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/25/
---
# 15일차

## 
https://www.heidisql.com/


## DB연결
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function(req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function(req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function(req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function(req, res, next) {

let 이름= "홍길동";
let 나이= "30";
res.render('dbselect', {
title: "DB_select",
name: 이름,
age: 나이,
});
});

module.exports = router;
```


### 이름,나이 추가
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function(req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function(req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function(req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function(req, res, next) {

client.query('SELECT * FROM testdatabase.USER;', function(err, result, fields){
if(err){
console.log("에러입니다.")
}else{
console.log("성공입니다.");
let 이름= result[0].name;
let 나이= result[0].age;
res.render('dbselect', {
title: "DB_select",
name: 이름,
age: 나이,
});
}
})
});

module.exports = router;
```

###

```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

// console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function (req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function (req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function (req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function (req, res, next) {

client.query('SELECT * FROM testdatabase.USER;', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
let 이름 = result[0].name;
let 나이 = result[0].age;
res.render('dbselect', {
title: "DB_select",
name: 이름,
age: 나이,
});
}
})
});

/* GET db connection page. */
router.get('/dbinsert', function (req, res, next) {

// let updated_at =;
// let created_at =;
client.query('INSERT INTO USER (name, age, created_at, updated_at)VALUES("홍길동","30","2022-10-25 11:07:25","2022-10-25 11:07:25");', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
// console.log(result);
console.log(result);

let insertId = result.insertId;
res.render('dbinsert', {
title: "DB_insert",
insertId: insertId,
});
}
});
});

module.exports = router;
```


### DB포스팅방식
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

// console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function (req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function (req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function (req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function (req, res, next) {

client.query('SELECT * FROM testdatabase.USER;', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
res.render('dbselect', {
title: "DB_select",
querySelect: result,
});
}
})
});

/* GET db connection page. */
router.get('/dbinsert', function (req, res, next) {

// let updated_at =;
// let created_at =;
client.query('INSERT INTO USER (name, age, created_at, updated_at)VALUES("홍길동","30","2022-10-25 11:07:25","2022-10-25 11:07:25");', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
// console.log(result);
console.log(result);

let insertId = result.insertId;
res.render('dbinsert', {
title: "DB_insert",
insertId: insertId,
});
}
});
});

router.post('/dbselect', function (req, res, next) {
res.render('dbselect', {
title: "DB_select_포스트방식으로들어옴",
name: "POST",
age: "나이",
});
});


module.exports = router;
```

### 조회하기
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

// console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function (req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function (req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function (req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function (req, res, next) {

client.query('SELECT * FROM testdatabase.USER;', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
res.render('dbselect', {
title: "DB_select",
result: result,
});
}
})
});

/* GET db connection page. */
router.get('/dbinsert', function (req, res, next) {

// let updated_at =;
// let created_at =;
client.query('INSERT INTO USER (name, age, created_at, updated_at)VALUES("홍길동","30","2022-10-25 11:07:25","2022-10-25 11:07:25");', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
// console.log(result);
console.log(result);

let insertId = result.insertId;
res.render('dbinsert', {
title: "DB_insert",
insertId: insertId,
});
}
});
});

router.post('/dbselect', function (req, res, next) {
res.render('dbselect', {
title: "DB_select_포스트방식으로들어옴",
name: "POST",
age: "나이",
});
});


module.exports = router;
```

```html
<!DOCTYPE html>
<html>
<head>
<title><%= title %></title>
<link rel='stylesheet' href='/stylesheets/style.css' />
</head>
<body>
<h1><%= title %></h1>


<table border="1px">
<thead>
<tr>
<td>#</td>
<td>이름</td>
<td>나이</td>
<td>생성일</td>
<td>수정일</td>
<td>기능</td>
</tr>
</thead>
<tbody>
<% for (let i=0; i<5; i++) { %>
<tr>
<td><%= result[i].id %></td>
<td><%= result[i].name %></td>
<td><%= result[i].age %></td>
<td><%= result[i].created_at %></td>
<td><%= result[i].updated_at %></td>
<td><button>수정하기</button><button>삭제하기</button></td>
</tr>
<% } %>
</tbody>
</table>

</body>
</html>
```


### DB 기능 업데이트

```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

// console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function (req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function (req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function (req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function (req, res, next) {

client.query('SELECT * FROM testdatabase.USER ORDER BY id DESC;', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
res.render('dbselect', {
title: "DB_select",
result: result,
});
}
})
});

/* GET db connection page. */
router.get('/dbinsert', function (req, res, next) {

// let updated_at =;
// let created_at =;
client.query('INSERT INTO USER (name, age, created_at, updated_at)VALUES("홍길동","30","2022-10-25 11:07:25","2022-10-25 11:07:25");', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
// console.log(result);
console.log(result);

let insertId = result.insertId;
res.render('dbinsert', {
title: "DB_insert",
insertId: insertId,
});
}
});
});


router.get('/dbselect/'+':id', function (req, res, next) {
client.query(`SELECT * FROM USER WHERE id=${req.params.id};`, function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("상세페이지조회 성공입니다.");
console.log(result);
res.render('dbselectdetail', {
title: "DB_select_각아이디의 상세페이지",
id: req.params.id,
name: result[0].name,
age: result[0].age,
address: result[0].address,
});
}
})
});

router.post('/dbselect', function (req, res, next) {
res.render('dbselect', {
title: "DB_select_포스트방식으로들어옴",
name: "POST",
age: "나이",
});
});


module.exports = router;
```

### 최종
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// db연결
let client = mysql.createConnection({
host: 'localhost',
port: '3306',
user: 'testuser',
password: 'testuserpw',
database: 'testdatabase',
})

// console.log(client);

// ajax
// 제이쿼리 아작스
// load() 외부 콘텐츠가져올때
// $.ajax() 아작스
// $.post() 포스트방식 응답받을때
// $.get() 겟방식 응답받을때
// $.getJSON() 겟방식으로 전달후 JSON으로 받을때
// $.getScript() 외부 자바스크립트 불러옴


/* GET home page. */
router.get('/', function (req, res, next) {
res.render('index', { title: 'Express' });
});

/* GET ajax page. */
router.get('/ajax', function (req, res, next) {
res.render('ajax', {
title: '아작스화면입니다.',
contents: '내용입니다.',
});
});

/* GET ajax html page. */
router.get('/ajaxhtml', function (req, res, next) {
res.sendFile('C:\\Users\\a\\expressproject\\views\\ajax.html');
});

/* GET db connection page. */
router.get('/dbselect', function (req, res, next) {
client.query('SELECT * FROM testdatabase.USER ORDER BY id DESC;', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
res.render('dbselect', {
title: "DB_select",
result: result,
});
}
})
});

/* GET db connection page. */
router.get('/dbinsert', function (req, res, next) {

// let updated_at =;
// let created_at =;
client.query('INSERT INTO USER (name, age, created_at, updated_at)VALUES("홍길동","30","2022-10-25 11:07:25","2022-10-25 11:07:25");', function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
// console.log(result);
console.log(result);

let insertId = result.insertId;
res.render('dbinsert', {
title: "DB_insert",
insertId: insertId,
});
}
});
});


router.get('/dbselect/'+':id', function (req, res, next) {
client.query(`SELECT * FROM USER WHERE id=${req.params.id};`, function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("상세페이지조회 성공입니다.");
console.log(result);
res.render('dbselectdetail', {
title: "DB_select_각아이디의 상세페이지",
id: req.params.id,
name: result[0].name,
age: result[0].age,
address: result[0].address,
});
}
})
});

router.post('/dbselect', function (req, res, next) {
res.render('dbselect', {
title: "DB_select_포스트방식으로들어옴",
name: "POST",
age: "나이",
});
});

router.get('/dbupdate/'+':id', function (req, res, next) {
let id = req.params.id;
// client.query(`UPDATE user SET name = "바뀐이름", age = "바뀐나이" WHERE id = ${id};`, function (err, result, fields) {
client.query(`UPDATE user SET name = "바뀐이름", age = "바뀐나이" WHERE id = ${id};`, function (err, result, fields) {
if (err) {
console.log("에러입니다.")
} else {
console.log("성공입니다.");
console.log(result);
res.render('dbupdate', {
title: "DB_update",
});
}
})
});


module.exports = router;
```