---
layout: post
title: "자바스크립트 1일차"
description: "자바스크립트 1일차"
categories: [Javascript]
tags: [Javascript]
redirect_from:
  - /2022/10/04/
---
# NODE JS 설치
https://nodejs.org/ko/download/

설치과정 : https://offbyone.tistory.com/441

자동리로드:https://dev.to/cassiolacerda/automatically-refresh-the-browser-on-node-express-server-changes-x1f680-1k0o

## 익스프레스 설치

npm i -g express-generator

## vscode 환경 설정
vscode-설정-autosave-afterDelay
vscode-확장-javascript(ES6), Prettier-Code formatter,auto close tag 설치

## 익스프레스 설치 후 기타파일 생성(node_modules등)

npm install

## 프로젝트 실행

npm start

npm start 이후 브라우저 : http://localhost:3000/ or http://127.0.0.1:3000/

###app,js에 추가작성


# 자바스크립트

## 자바스크립트란?

웹페이지에 동적인 생동감을 불어넣는 것

예전에는 자바 자바스크립트, 라이브스크립트, ECMAScript라 했으나 현재는 자바스크립트로 거의 공용되었다

test

# Fenced Code Blocks

~~~~~~~~~~~~
~~~~~~~
code with tildes
~~~~~~~~
~~~~~~~~~~~~~~~~~~

# Simple codeblock with long lines

    function myFunction() {
        alert("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
    }

# Language of Code Blocks

~~~ ruby
def what?
  42
end
~~~

# Highlighted

## External Gist

<script src="https://gist.github.com/yizeng/9b871ad619e6dcdcc0545cac3101f361.js"></script>

## Simple Highlight

{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}

## Highlight with long lines

{% highlight c# %}
public class Hello {
    public static void Main() {
        Console.WriteLine("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
    }
}
{% endhighlight %}

## Highlight with line numbers and long lines

{% highlight javascript linenos=table %}
function myFunction() {
    alert("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
}
{% endhighlight %}

[^1]: This is a footnote.

[kramdown]: https://kramdown.gettalong.org/
[Simple Texture]: https://github.com/yizeng/jekyll-theme-simple-texture