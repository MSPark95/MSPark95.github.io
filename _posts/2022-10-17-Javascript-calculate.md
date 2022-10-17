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

```html
<!DOCTYPE html>
<html lang="kr">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>Document</title>
</head>
<body>
  <div class="calc">
		<div class="display-container">
            <div class="display">0</div>
        </div>
        <button class="button all-clear">AC</button>
        <button class="button operation">()</button>
        <button class="button operation">%</button>
        <button class="button operation">&#247</button>
        <button class="button number">7</button>
        <button class="button number">8</button>
        <button class="button number">9</button>
        <button class="button operation">×</button>
        <button class="button number">4</button>
        <button class="button number">5</button>
        <button class="button number">6</button>
        <button class="button operation">-</button>
        <button class="button number">1</button>
        <button class="button number">2</button>
        <button class="button number">3</button>
        <button class="button operation">+</button>
        <button class="button number">&#177</button>
        <button class="button number">0</button>
        <button class="button number">.</button>
        <button class="button operation">=</button>
    </div>

    <script>

    </script>
</body>
</html>
```

```css
.calc {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

.display-container {
  grid-column: span 4;
}
```