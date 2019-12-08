---
title: JavaScript 변수 var, let, const
date: "2019-08-08T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-javascript-variable/"
category: "JavaScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
  - "변수"
description: "JavaScript 변수 var, let, const"
---

자바스크립트 공부를 진행하며
배운 변수 var / let / const에 대해 정리하는 글입니다 !

## 변수의 종류

### 1. var 전역변수

- var의 scope는 global
  (함수밖에서 정의 된 변수가 함수 안에서도 사용가능하고,whole window 안에서 사용 다 가능한 것)

```javascript
var greeting = "hey hi";
var times = 4;
if (times > 3) {
  var greeting = "say Hello instead";
}
console.log(greeting);
//출력: "say Hello instead"
```

변수 greeting 이 {} 안에서 재정의 되었는데... 값이 바뀌어버림
동일한 변수명쓰면, 값이 달라지는 에러 등이 발생할 수 있음
-> let 과 const의 사용이 필수적임!

- 변수 var는 중복 사용 가능(여러번 값 할당가능)

![image.png](https://images.velog.io/post-images/haileyself/5cd00920-faf5-11e9-a375-835ec727f36f/image.png)

### 2. let

- let은 ES6부터 사용되는 local variable (지역변수)
- block level scope를 가짐 -> block안에서만 역할 가능 !
- block은 { } 로 묶인 공간이며 이런 변수는 scope가 정해진 경우, 해당 scope에서만 변수역할을 할 수 있음!
  (예를 들어 function안에서 let을 통해 변수를 정해줬는데
  내가 함수 밖에서 해당 변수를 호출하면 해당변수는 undefined으로 나옴! 값이 나오지않는다~~)
- 변수로 저장된 데이터 값을 바꿀 수 있음(값 update 가능)
- 같은 scope 내에서 redeclaration 안됨 !

```javascript
let greeting = "say Hi";
let greeting = "say Hello instead";
// error : 이미 declared된 것이다 라는 에러 뜸

let b = 1;
{
  let b = 2;
  console.log(b);
}
console.log(b);
// 출력값 : 2 와 1
// 다른 block에서 선언되었기때문에 에러메세지 뜨지 않음
// scope가 block으로 한정된 다는 것을 확인 가능
```

### 3. const

- const도 ES6부터 등장한 지역변수
- block level scope
- 변수로 저장된 데이터 값을 바꿀 수 없음(reassignment 불가)

![image.png](https://images.velog.io/post-images/haileyself/e26c7bd0-faf6-11e9-8e8c-85968af1b216/image.png)

- 같은 scope에서 redeclaration 안됨!
- mutable state를 줄이기 최소화하기 위해서 const 사용

**일단은 const를 통해서 변수를 쓰는 습관을 들이고, 나중에 수정할 일 있을 때 let으로 변경해주면 된다 !**

### 4. 호이스팅(Hoisting)

자바스크립트에서 변수가 호출된 이후에 변수가 선언되었음에도 불구하고, 변수선언이 호출 이전에 된 것처럼 실행되는 현상
(scope 내에서 변수선언부분이 아래에 적혀있어도, 맨 위에 선언된 것 처럼 일어나는 현상)

#### 1. var의 호이스팅

```js
console.log(a);
var a;
//출력값: undefined;
```

- var는 변수가 선언되면, 선언과 초기화(undefined)가 한번에 이루어진다. 이를 통해 선언되는 순간 변수가 실행되고, 초기화를 통해 변수 객체에 등록된 변수를 위한 공간을 메모리에 확보한다.
  -> undefined으로 일단 선언됨(값 할당 전)
  -> error msg가 "undefined"로 뜸

#### 2. let, const의 호이스팅

- let 과 const도 호이스팅이 발생
- let / const는 선언과 초기화가 분리되어서 발생
- 초기화 전까지 변수참조가 없고, 이래서 참조에러가 발생함(scope에 변수가 등록되었으나, 공간을 메모리에 확보하지 못하여 변수를 참조할 수 없는 이 사이를 TDZ(Temporal Dead Zone)이라고 부름
- 에러메세지가 var와 달리, 초기화 이전이다라고 뜸 !

![image.png](https://images.velog.io/post-images/haileyself/3a5f5370-faf8-11e9-98ed-4f42a40f0442/image.png)
