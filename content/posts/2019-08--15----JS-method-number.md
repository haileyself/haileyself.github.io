---
title: JavaScript 숫자 관련 Method
date: "2019-08-15T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-method-number/"
category: "JavaScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
  - "method"
description: "JavaScript 숫자 관련 Method"
---

Javascript에서 쓰는 숫자 관련 method를 정리해보았다 :)

## Javascript 숫자 관련 Method

### 1. Math.round

수를 반올림해주는 method!
절반 미만이면 0으로 마지막 값을 버려주고, 절반 이상이면 0으로 마지막 값을 버려주고 윗자리에 1을 더한다.

```javascript
Math.round(2.5);
console.log(Math.round(2.5));
// 출력 : 3

Math.round(2.49);
console.log(Math.round(2.49));
//출력: 2
```

반올림 함수는 평점을 표시하는 별과 같은 요소들을 만들 때 사용한다.
평균평점이 3.86과 같은 수일 때,
평점을 별로 표현해야한다면? 3.86으로 하면 깔끔하게 화면에 표시하기가 힘듬.
그래서 3개나 4개 이런식으로 딱 떨어지는 수로 칠해야 함 .
그럴 때는 반올림 값을 구해서 해당하는 별에 색칠을 해주는 식으로 코딩을 해야 함 !

### 2. Math.ceil()

올림하는 함수로 괄호 안 숫자의 소수점 첫째자리 값을 버리고 +1 해주는 함수

```javascript
Math.ceil(2.49);
console.log(Math.ceil(2.49));
//출력: 3
```

### 3. Math.floor()

내림 함수로 괄호 안의 값을 내려주는 함수

```javascript
Math.floor(2.49);
console.log(Math.floor(2.49));
// 출력: 2
```

### 4. Math.random

랜덤함수 : 0부터 1사이의 랜덤한 숫자를 골라서 출력해주는 함수, 매개변수가 없는 함수!

```javascript
let ranNum = Math.random;
Math.floor(ranNum * 10);
// 1부터 10 사이의 랜덤한 숫자를 골라서 출력하는 함수를 만들 수 있음 !
```

**- 최소 값, 최대 값을 받아 그 사이의 랜덤한 수를 리턴하는 함수를 구현하는 방법**

```javascript
function getRanNum(min, max) {
  let ranNum = Math.random();
  return ranNum * (max - min) + min;
}
```

해당 함수는 소수점이 있는 수를 리턴하기 때문에, 정수인 리턴 값을 구하고 싶으면 Math.floor method를 사용하면 된다 !
