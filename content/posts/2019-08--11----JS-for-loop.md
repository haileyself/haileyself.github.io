---
title: JavaScript for loop
date: "2019-08-11T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-javascript-for-loop/"
category: "JavaScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
  - "for문"
  - "for loop"
description: "JavaScript for loop"
---

자바스크립트의 반복문 중 하나인 for문에 대해 배운내용을 정리해보았습니다.

## 1. for문

### 1. for문이란?

for 문은 무언가를 반복적으로 실행해주고 싶을 때 사용하는 것.
우리가 원하는 만큼 코드를 반복시켜줌.
언제부터 언제까지라고 반복조건을 알려주면 그만큼 반복 가능
i 라는 변수의 값을 정해서 for ( ) 소괄호에 있는 반복조건만큼, { } 중괄호에 있는 코드가 계속 실행되게 하는 기능이다!

```javascript
let count = 1;
for (let i = 0; i < 6; i++) {
  count = count + 1;
}
```

i 는 0 에서 시작해서 i 가 6보다 작을때까지, i 값은 i = i + 1로 1씩 증가하면서 i 가 6보다 작을때까지 조건에 맞으면 count = count + 1 이라는 함수가 계속 실행된다.
그래서 총 6번 돌면,

```
1회 > 1 + 1 -> 2  (여기서 i = 0)
2회 > 2 + 1 -> 3 (여기서 i = 1)
3회 > 3 + 1 -> 4 (여기서 i = 2)
4회 > 4 + 1 -> 5 (여기서 i = 3)
5회 > 5 + 1 -> 6 (여기서 i = 4)
6회 > 6 + 1 -> 7 (여기서 i = 5)
총 6번 반복하면 나오는 값은 7 이다 !
```

### 2. for 문 작성방법

```javascript
 for (반복조건) {
  // 반복조건이 맞으면 실행할 코드
  }
```

### 3. for문 내부의 if 문 해석

```javascript
const home = "대전";
let cities = ["서울", "대전", "대구", "부산", "광주", "제주도"];

for (let i = 0; i <= 5; i++) {
  if (cities[i] === home) {
    console.log("아, " + cities[i] + " 사시는군요");
  }
}
// 출력: 아 , 대전 사시는군요
```

for가 0일때, cities[0] 과 home을 비교하는데, 같지않으므로 if 로 들어가지않고
for문이 계속 실행된다. cities[1] === home 동일, 동일하면 if 문 실행 !
i가 5가 될 때까지 조건을 if 조건을 확인하며 for 문이 실행되고 끝.

<참고>
i 값의 변화 / 반복문이 잘 도는지를 알고싶으면 for문 안에도 개발자도구를 통해서 console을 찍어 보면 된다 !

i 가 5가 될때까지 반복문은 실행되고, 중간에 1번째에 있는 배열의 값이 home 의 대전값과 일치할 때 if 안에 있는 조건문이 실행되었음을 알 수 있다 !

### 4. 이중 for문

for문안에 for문을 중첩해서 쓸 수 있다.
Ex. 문자 뒤에 글씨 00부터~ 99까지 나오게 하는 방법

```javascript
for (let i = 0; i < 10; i++) {
  for (let j = 0; j < 10; j++) {
    console.log("Hi EveryBody" + i + j);
  }
}
```

이렇게 하면 i 가 0 일때, j 가 0부터 9까지 돌고 i 가 1일때, j가 0부터 9까지 돌고…..i 가 9일때까지 j가 0-9까지 돌아서
HiEverybody00 ~ HiEverybody99까지 콘솔로 찍어서 볼 수 있다 !

![image.png](https://images.velog.io/post-images/haileyself/e9d64e10-1a85-11ea-832c-25e84034b85b/image.png)
이런식으로 쭉 99까지 나온다 !
