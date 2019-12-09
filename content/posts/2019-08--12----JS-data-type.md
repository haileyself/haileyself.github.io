---
title: JavaScript Data Type
date: "2019-08-12T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-datatype/"
category: "JavaScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
  - "datatype"
  - "데이터타입"
description: "JavaScript Data Type"
---

자바스크립트의 데이터타입에 대해 구분하고 정리해보았습니다.

## Javascript Data Type

### 1. typeof 연산자

typeof 연산자를 사용하면 해당 값/ 변수가 무슨 데이터 타입인지 알 수 있다.

```javascript
typeof 1;
// 출력 : “number”
typeof name;
// 출력 : “string“
```

### 2. Javascript data의 종류

#### 1. undefined

정의되지않은 변수로,변수를 정의할 때 초기화하지않았다면 변수에는 undefined가 할당된다.

```js
typeof a;
//출력: “undefined”
let msg;
typeof msg;
//출력: “undefined”
```

**변수의 초기화란 ? 선언한 변수에 처음으로 값을 저장하는 과정**

```javascript
var a; // 변수만 선언한 것
var a = value; //변수 초기화 한 것 !
```

#### 2. null

Javascript의 원시값 중 하나로, 어떤 값이 의도적으로 비어있음을 표현함

- 해당 값은 typeof(null); 하면 object라고 출력 됨
  식별되지않은 상태를 나타내고, 해당 변수가 어떠한 객체도 가리키고 있지않을 때 사용(undefined 과는 다름), 말 그대로 아무것도 아닌 빈객체를 가르키고 있음

#### 3. Boolean

true / false 두가지 value를 가지고 있는 값을 말함

```javascript
typeof (1 === 1);
// 출력:  “boolean”
typeof (1 === 2);
// 출력:  “boolean”
typeof true;
// 출력: “boolean”
typeof false;
// 출력: “boolean”
```

- 참고!
  다른 데이터 타입이 boolean 으로 변환되는 경우가 여러 개 있음

  (1) true로 변환되는 값

  - 문자열 : 비어있지않은 문자열 모두
  - 숫자 : 0이 아닌 모든 숫자
  - 객체 : 모든 객체

  (2) false로 변환되는 값

  - 문자열: “ “ (빈문자열)
  - 숫자 : 0
  - NaN
  - 객체: null
  - undefined

#### 4. number

모든 숫자는 다 number로 typeof(1); → number;로 나옴 !

#### 5. string

문자열 “”/ ‘’ 로 시작하는 값은 string으로 출력 됨 !

#### 참고

배열은 typeof()로 확인하면 “object”로 출력된다 !
배열은 확장된 객체이다~ 이정도만 기억하고 넘어가자 :)
