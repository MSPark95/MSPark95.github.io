---
layout: post
title: "Javascript 16일차"
description: "Javascript 16일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/26/
---
# 16일차

## DB업데이트
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// orm 각orm 문법이 다름
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

```html
<!DOCTYPE html>
<html>
<head>
<title><%= title %></title>
<link rel='stylesheet' href='/stylesheets/style.css' />
</head>
<body>
<h1><%= title %></h1>
<h1>잘 업데이트 되었습니다. 목록돌아갑니다.</h1>
<script>
setTimeout(function() {
//window.location.href = 'http://localhost:3001/dbselect';
window.location.href = '/dbselect';
},3000)
</script>
</body>
</html>
```


### 
```javascript
// index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// orm 각orm 문법이 다름
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
client.query('SELECT * FROM USER ORDER BY id DESC;', function (err, result, fields) {
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

router.get('/dbdelect/'+':id', function (req, res, next) {
client.query(`DELETE FROM user WHERE id=${req.params.id};`, function (err, result, fields) {
if (err) {
console.log("삭제에러입니다.")
} else {
console.log("삭제성공입니다.");
console.log(result);
res.render('dbdelete', {
title: "DB_deleete_삭제후 페이지",
id: req.params.id,
});
}
})
});

module.exports = router;
```

### 
```html
<!DOCTYPE html>
<html>
<head>
<!--Import Google Icon Font-->
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
<!--Import materialize.css-->
<!-- <link type="text/css" rel="stylesheet" href="css/materialize.min.css" media="screen,projection"/> -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">
<!--Let browser know website is optimized for mobile-->
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
</head>

<body>
<div class="container">
<h2><%= title %></h2>
</div>
<div class="container">
<div class="row">
<form class="col s12" >
<div class="row">
<div class="input-field col s6">
<input placeholder="이름을 입력하세요" id="name" type="text" class="validate">
<label for="name">이름</label>
</div>
<div class="input-field col s6">
<input placeholder="나이를 입력하세요" id="age" type="text" class="validate">
<label for="age">나이</label>
</div>
<div class="input-field col s12">
<input placeholder="주소를 입력하세요" id="address" type="text" class="validate">
<label for="address">주소</label>
</div>
</div>
<div class="row">
<button class="btn waves-effect waves-light" type="submit" name="action">Submit
<i class="material-icons right">send</i>
</button>
</div>
</form>
</div>
</div>
<!--JavaScript at end of body for optimized loading-->
<!-- <script type="text/javascript" src="js/materialize.min.js"></script> -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>
</body>
</html>
```


### 머터리얼css사용법

```javacript
/ index.js
var express = require('express');
var router = express.Router();
const mysql = require('mysql');
// orm 각orm 문법이 다름
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
client.query('SELECT * FROM USER ORDER BY id DESC;', function (err, result, fields) {
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
router.get('/dbinsertform', function (req, res, next) {
res.render('dbinsertform', {
title: "DB_유저추가화면입니다.",
});
});

/* GET db connection page. */
router.get('/dbinsert', function (req, res, next) {
let name = req.query.name;
let age = req.query.age;
let address = req.query.address;
let condition = req.query.condition;
let created_at = req.query.created_at;
let updated_at = req.query.updated_at;
console.log(`넘어온값은${name}`);
console.log(`넘어온값은${age}`);
console.log(`넘어온값은${address}`);
console.log(`넘어온값은${condition}`);
console.log(`넘어온값은${created_at}`);
console.log(`넘어온값은${updated_at}`);
client.query(`INSERT INTO testdatabase.user (name) VALUES ("dfsf");`, function (err, result, fields) {
if (err) {
console.log("인서트에러입니다.")
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

router.get('/dbdelect/'+':id', function (req, res, next) {
client.query(`DELETE FROM user WHERE id=${req.params.id};`, function (err, result, fields) {
if (err) {
console.log("삭제에러입니다.")
} else {
console.log("삭제성공입니다.");
console.log(result);
res.render('dbdelete', {
title: "DB_deleete_삭제후 페이지",
id: req.params.id,
});
}
})
});

module.exports = router;
```


### 참고사이트
유사한 사이트 찾아주는 곳 : https://alternativeto.net/

머터리얼css 사이트
https://materializecss.com/
https://materializecss.com/getting-started.html
~~~~~~~~~~~~~~~
https://materializecss.com/text-inputs.html

내도메인 찾는곳
https://www.findip.kr/
