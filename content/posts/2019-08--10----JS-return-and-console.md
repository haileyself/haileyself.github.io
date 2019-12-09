---
title: JavaScript 함수의 return 그리고 console.log 관련 참고사항
date: "2019-08-10T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-javascript-return-n-console/"
category: "JavaScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
  - "함수"
  - "return"
  - "console.log"
description: "JavaScript 함수에서 return , 그리고 console.log 관련 참고사항"
---

Javascript session을 통해서 배운 함수에서의 return 은 어디에 위치해야 하는지와 console.log를 찍을 때 참고해야 될 사항을
정리해보았습니다.

## 1. JS 함수에서 return의 위치

**함수 안에서 return을 넣는 경우에는 함수가 끝나는 곳에 넣어야한다**

- why? return 이라는 말을 만나면 함수는 값을 내뱉고 끝나게 됨!

```javascript
	function addFirestAndLast(myArray) {
	   return (myArray[0] + myArray[2]) ;
 	   if(조건) {
	    }
	   else(조건) {
                }
	    }
// 해당 함수의 if 조건 안에 statement 실행 안됨 !
// 왜? return하면 함수 끝 !
```

## 2. console.log

**코드를 짜고 나서 가장 중요한 것 ! console.log 찍는 습관 들이기**

- 개발자도구를 열어서 console.log(알고자하는 값)을 찍어보기
- console.log () 란?
  자바스크립트에서 이전에 정의 된 변수들을 화면에 출력하거나 사용자에게
  보여줘야되는 어떤 메시지를 출력하기 위해서 사용하는 기능.
- console이라는 객체의 log 함수(method)라고 보면 된다.
- console.log() --> 괄호에는 어떤 것이든지 올 수 있다. (string / num / array / 객체 등)

```javascript
var a = 2;
console.log(a);
// 출력: 2 ;
var str = "coding";
console.log(str);
// 출력 값 : coding
```

내가 변수를 잘 설정했는지, 해당 함수가 제대로 실행되고 있는지, 변수값이 어떻게 변하고 있는지 이런것들을 확인해보기 위해서 console.log를 꼭 해보자 !
console.log를 할 때 여러번 콘솔을 찍어보면 값이 헷갈리니깐 콘솔찍는 부분에 ' ' string으로 설명 표시를 하기

```javascript
console.log("이거는 처음 정한 변수", a);
```

- 디버깅(오류를 없애는 것)을 할때 가장 중요한 요소가 console을 쳐서 어디서부터가 문제인지 아는 것 !

#### 1. console.log 찍어서 나오는 오류의 종류

- NaN

Not a number - 자바스크립트에서는 숫자 + string도 더하기 값이 계산 됨 !
그러나 '\*'(곱셈) 은 안됨
그럴 때 숫자가 아니라 계산 못했어라는 에러 메세지(NaN)가 나옴

- sth(변수이름) is not defined

  변수가 선언 된 적이 없는데 쓰면 뜨는 오류

- undefined

  인자로 아무것도 안보냈을 때 뜨는 오류 / 콘솔은 인자가 필요한데 () 괄호값에 아무것도 안넣어주면 undefined라고 뜸 undefined는 하나의 데이터 타입이다. - undefined type은 어떤 변수에 어떤 값도 할당되지않았을 때 undefined 라는 datatype을 사용 !

- sth(이름) is not a function
  함수가 아닌데 함수로 호출하면 뜨는 오류

#### 2. console.log 시에 주의할 점 !

에러가 발생하기 직전의 위치에 console.log를 찍어보기
에러가 나면 해당 코드가 실행되지않고 종료되기때문에 console을 쳐서 어디가 문제인지 알아야 한다
