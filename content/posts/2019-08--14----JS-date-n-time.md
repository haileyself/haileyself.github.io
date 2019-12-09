---
title: JavaScript 날짜와 시간 표현방법
date: "2019-08-14T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-date-n-time/"
category: "JavaScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
  - "date"
  - "time"
description: "JavaScript 날짜와 시간 표현방법"
---

오늘 배운 내용인
Javascript로 날짜와 시간을 표현하는 방법을 정리해보았다 !

## Javascript에서의 날짜와 시간

- 날짜와 시간을 저장하고 보여줄 때, 날짜 객체를 사용한다.
- 날짜 객체를 호출 시 쉽게 시간과 날짜를 얻을 수 있음
- 날짜 객체 생성법

```javascript
let rightNow = new Date();
// ()안에는 숫자 값은 ' ' string화 해서 올리기
```

- 호출하는 법

```javascript
console.log(rightNow);
//출력: Sun Aug 18 2019 21:48:31 GMT+0900 (한국 표준시)
// JavaScript 날짜와 시간 표현방법
```

현재 new Date()를 하니 출력되는 값이 상위와 같았다.
new Date()를 했을 때 브라우저마다 표현하는 법이 다르다.
그리고 위에 출력된 날짜, 시간정보는 사람이 읽기좋은 표현으로 나온 것이라,코딩을 할 때는 new Date() 에서 반환된 표현을 그대로 사용하진 않음

개발자는 new Date()를 통해 현재시간, 날짜 정보를 가져온 후에,
아래처럼 디자이너가 요구하는 날짜 포맷으로 웹사이트에 보여주게끔 날짜, 시간표현 방식을 바꿔준다.

```
Ex. 2월 18일 월요일 19:45
```

### 1. 날짜 관련 Method

#### 1. getFullYear();

new Date()에서 출력된 값에서 년도를 가져온다

```javascript
let d = new Date();
let year = d.getFullYear();
// 출력: 2019; 2019년
```

#### 2. getMonth();

new Date()에서 출력된 값에서 달을 가져오는 method

- 달의 값을 0~11로 출력, 0이 1월 ,11이 12월이므로 현재의 달을 표현하기 위해서는getMonth() 출력값의 +1 을 해야함

```javascript
let d = new Date();
let month = d.getMonth();
//출력 : 7 ;  8월
// 출력은 7이기때문에, +1 해서 현재 달이 8월이라는 걸 알아야함 !
```

#### 3. getDate();

: 현재 날짜의 날짜값을 가져온다

```javascript
let d = new Date();
d.getDate();
// 출력: 18; 18일
```

#### 4. getDay();

현재 날짜의 요일 값을 가져온다

- 숫자로 출력한다, 0~6으로 나타나며 일요일-토요일을 나타낸다.
  0은 일요일, 1은 월요일이다.

```javascript
let d = new Date();
d.getDay();
// 출력: 0; 일요일
```

#### 5. getHours();

현재 new Date()로 출력한 값의 시간에 해당하는 값을 출력한다.

- 숫자로 출력된다.

```javascript
let d = new Date();
d.getHours();
// 출력: 21; 21시
```

#### 6. getMinutes();

new Date()로 출력한 분에 해당하는 값이 나타남

```javascript
let d = new Date();
d.getHours();
// 출력: 59; 59분
```
